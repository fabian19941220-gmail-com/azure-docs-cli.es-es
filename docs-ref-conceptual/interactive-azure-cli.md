---
title: Modo interactivo de la CLI de Azure
description: Use la CLI de Azure en modo interactivo.
author: dbradish-microsoft
ms.author: dbradish
manager: barbkess
ms.date: 09/09/2018
ms.topic: conceptual
ms.service: azure-cli
ms.devlang: azurecli
ms.openlocfilehash: 7b3ee1e284e7f771c661bb65bf8b8ab53dafd77f
ms.sourcegitcommit: 7caa6673f65e61deb8d6def6386e4eb9acdac923
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77779523"
---
# <a name="azure-cli-interactive-mode"></a>Modo interactivo de la CLI de Azure

Puede usar la CLI de Azure en modo interactivo mediante la ejecución del comando `az interactive`.
Este modo abre un shell interactivo con función autocompletar, descripciones de los comandos y ejemplos.

![modo interactivo](./media/interactive-azure-cli/webapp-create.png)

> [!NOTE]
> Aquí no se va a usar el estilo predeterminado, ya que no se lee sobre un fondo negro.

Si aún no ha iniciado sesión en la cuenta, use el comando `login`.

## <a name="configure"></a>Configuración

El modo interactivo muestra de manera opcional descripciones de comandos, descripciones de parámetros y ejemplos de comandos.
Active o desactive las descripciones y los ejemplos con `F1`.

![descripciones y ejemplos](./media/interactive-azure-cli/descriptions-and-examples.png)

Puede activar o desactivar la visualización de los parámetros predeterminados mediante `F2`.

![parámetros predeterminados](./media/interactive-azure-cli/defaults.png)

`F3` alterna la visualización de algunos gestos clave.

![gestos](./media/interactive-azure-cli/gestures.png)

## <a name="scope"></a>Ámbito

Puede establecer el ámbito del modo interactivo a un grupo de comandos específico, como `vm` o `vm image`.
Al hacerlo, todos los comandos se interpretan en ese ámbito.
Se trata de un método abreviado ideal si va a realizar todo el trabajo en dicho grupo de comandos.

En lugar de escribir estos comandos:

```azurecli
az>> vm create -n myVM -g myRG --image UbuntuLTS
az>> vm list -o table
```

Puede definir el ámbito del grupo de comandos de máquina virtual y escribir estos comandos:

```azurecli
az>> %%vm
az vm>> create -n myVM -g myRG --image UbuntuLTS
az vm>>list -o table
```

También puede definir el ámbito en grupos de comandos de nivel inferior.
Podría definir el ámbito en `vm image` mediante `%%vm image`.
En este caso, puesto que el ámbito ya está definido en `vm`, se usaría `%%image`.

```azurecli
az vm>> %%image
az vm image>>
```

En ese punto, se puede devolver el ámbito a `vm` mediante `%%..`, o bien se puede definir el ámbito en la raíz solo con `%%`.

```azurecli
az vm image>> %%
az>>
```

## <a name="query"></a>Consultar

Puede ejecutar una consulta JMESPath en los resultados del último comando ejecutado utilizando `??` seguido de una consulta JMESPath.
Por ejemplo, después de crear un grupo, puede recuperar el identificador del nuevo grupo.

```azurecli
az>> group create -n myRG -l westEurope
az>> "?? id"
```

También puede usar esta sintaxis para usar el resultado del comando anterior como un argumento del siguiente comando.* Por ejemplo después de enumerar todos los grupos, se muestran todos los recursos del tipo `virtualMachine` en el primer grupo cuya ubicación sea westeurope. 

```azurecli
az>> vm create --name myVM --resource-group myRG --image UbuntuLTS --no-wait -o json
az>> group list -o json
az>> resource list -g "?? [?location=='westeurope'].name | [0]" --query "[?type=='Microsoft.Compute/virtualMachines'].name
```

Para más información sobre cómo consultar los resultados de los comandos, examine [Consulta de resultados de los comandos con la CLI de Azure](query-azure-cli.md).

## <a name="bash-commands"></a>Comandos de Bash

Puede ejecutar comandos shell sin salir del modo interactivo mediante `#[cmd]`.

```azurecli
az>> #dir
```

## <a name="examples"></a>Ejemplos

Algunos comandos tienen una gran cantidad de ejemplos.
Puede desplazarse a la siguiente página de ejemplos con `CTRL-N` y a la página anterior mediante `CTRL-Y`.

![ejemplos](./media/interactive-azure-cli/examples.png)

También puede ver un ejemplo concreto mediante `::#`.

```azurecli
az>> vm create ::8
```
