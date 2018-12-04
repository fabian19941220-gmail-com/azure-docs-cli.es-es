---
author: sptramer
ms.author: sttramer
manager: carmonm
ms.date: 11/26/2018
ms.topic: include
ms.openlocfilehash: ee0b2b0c8c557aa54255f28429bb3a174c0e21a9
ms.sourcegitcommit: a8aac038e6ede0b1b352ca6163a04b61ff4eed5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "52450350"
---
### <a name="cli-fails-to-install-or-run-on-windows-subsystem-for-linux"></a><span data-ttu-id="3ddc3-101">Se produce un error en la CLI al instalar o ejecutar en el subsistema de Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="3ddc3-101">CLI fails to install or run on Windows Subsystem for Linux</span></span>

<span data-ttu-id="3ddc3-102">Como el [subsistema de Windows para Linux (WSL)](/windows/wsl/about) es una capa de traducción de llamadas del sistema que se ejecuta en la plataforma Windows, es posible que experimente un error al intentar instalar o ejecutar en la CLI de Azure.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-102">Since [Windows Subsystem for Linux (WSL)](/windows/wsl/about) is a system call translation layer on top of the Windows platform, you might experience an error when trying to install or run the Azure CLI.</span></span> <span data-ttu-id="3ddc3-103">La CLI se basa en algunas características que podrían producir un error en WSL.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-103">The CLI relies on some features that may have a bug in WSL.</span></span> <span data-ttu-id="3ddc3-104">Si experimenta un error, independientemente de cómo instale la CLI, es muy probable que se trate de un problema de WSL y no del proceso de instalación de la CLI.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-104">If you experience an error no matter how you install the CLI, there's a good chance it's an issue with WSL and not with the CLI install process.</span></span>

<span data-ttu-id="3ddc3-105">Para solucionar los problemas de instalación de WSL:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-105">To troubleshoot your WSL installation and possibly resolve issues:</span></span>

* <span data-ttu-id="3ddc3-106">Si puede, ejecute un proceso de instalación idéntico en una máquina Linux para ver si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-106">If you can, run an identical install process on a Linux machine or VM to see if it succeeds.</span></span> <span data-ttu-id="3ddc3-107">Si es así, su problema seguramente está relacionado con WSL.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-107">If it does, your issue is almost certainly related to WSL.</span></span> <span data-ttu-id="3ddc3-108">Para iniciar una máquina virtual Linux en Azure, consulte [Creación de una máquina virtual Linux en Azure Portal](/azure/virtual-machines/linux/quick-create-portal).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-108">To start a Linux VM in Azure, see the [create a Linux VM in the Azure Portal](/azure/virtual-machines/linux/quick-create-portal) documentation.</span></span>
* <span data-ttu-id="3ddc3-109">Asegúrese de que usa la versión más reciente de WSL.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-109">Make sure that you're running the latest version of WSL.</span></span> <span data-ttu-id="3ddc3-110">Para obtener la última versión, [actualice su instalación de Windows 10](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-110">To get the latest version, [update your Windows 10 installation](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
* <span data-ttu-id="3ddc3-111">Consulte los [problemas abiertos](https://github.com/Microsoft/WSL/issues) con WSL que pudieran resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-111">Check for any [open issues](https://github.com/Microsoft/WSL/issues) with WSL which might address your problem.</span></span>
  <span data-ttu-id="3ddc3-112">Suele haber sugerencias sobre cómo solucionar el problema o información sobre una versión donde se corregirá el problema.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-112">Often there will be suggestions on how to work around the problem, or information about a release where the issue will be fixed.</span></span>
* <span data-ttu-id="3ddc3-113">Si no hay ninguna incidencia abierta para su problema, [abra una incidencia nueva con WSL](https://github.com/Microsoft/WSL/issues/new) y asegúrese de incluir toda la información posible.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-113">If there are no existing issues for your problem, [file a new issue with WSL](https://github.com/Microsoft/WSL/issues/new) and make sure that you include as much information as possible.</span></span>

<span data-ttu-id="3ddc3-114">Si aún tiene problemas para instalar o ejecutar en WSL, considere la posibilidad de [instalar la CLI para Windows](../install-azure-cli-windows.md).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-114">If you continue to have issues installing or running on WSL, consider [installing the CLI for Windows](../install-azure-cli-windows.md).</span></span>