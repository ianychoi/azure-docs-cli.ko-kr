---
title: Azure CLI 1.0 설치 | Microsoft Docs
description: Mac, Linux 및 Windows용 Azure CLI 1.0을 설치하여 Azure 서비스 사용 시작
editor: ''
manager: timlt
documentationcenter: ''
author: squillace
services: virtual-machines-linux,virtual-network,storage,azure-resource-manager
tags: azure-resource-manager,azure-service-management
ms.assetid: bdb776c8-7a76-4f3a-887c-236b4fffee10
ms.service: multiple
ms.workload: multiple
ms.tgt_pltfrm: command-line-interface
ms.devlang: na
ms.topic: article
ms.date: 03/20/2017
ms.author: rasquill
ms.openlocfilehash: 1c57e920c52f7f324c32fd457165bbafbda19b21
ms.sourcegitcommit: d9e5743a4321684c412c1740d26e7c1e258af5b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2018
---
# <a name="install-the-azure-cli-10"></a><span data-ttu-id="f6c56-103">Azure CLI 1.0 설치</span><span class="sxs-lookup"><span data-stu-id="f6c56-103">Install the Azure CLI 1.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6c56-104">이 항목에서는 Azure CLI 1.0을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-104">This topic describes how to install the Azure CLI 1.0.</span></span> <span data-ttu-id="f6c56-105">이 CLI는 사용되지 않으므로 "클래식" 리소스를 포함한 ASM(Azure 서비스 관리) 모델의 지원에서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-105">This CLI is deprecated and should only be used for support with the Azure Service Management (ASM) model with "classic" resources.</span></span>
> <span data-ttu-id="f6c56-106">Azure Resource Manager 배포의 경우 [Azure CLI 2.0](/cli/azure)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-106">For Azure Resource Manager deployments, use [Azure CLI 2.0](/cli/azure).</span></span>

<span data-ttu-id="f6c56-107">신속하게 Azure CLI 1.0(Azure 명령줄 인터페이스)을 설치하여 Microsoft Azure에서 리소스를 만들고 관리하기 위한 오픈 소스 셸 기반 명령 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-107">Quickly install the Azure Command-Line Interface (Azure CLI 1.0) to use a set of open-source shell-based commands for creating and managing resources in Microsoft Azure.</span></span> <span data-ttu-id="f6c56-108">컴퓨터에 크로스 플랫폼 도구를 설치하는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-108">You have several options to install these cross-platform tools on your computer:</span></span>

* <span data-ttu-id="f6c56-109">**npm 패키지** - npm(JavaScript용 패키지 관리자)을 실행하여 Linux 배포 또는 OS에 최신 Azure CLI 1.0 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-109">**npm package** - Run npm (the package manager for JavaScript) to install the latest Azure CLI 1.0 package on your Linux distribution or OS.</span></span> <span data-ttu-id="f6c56-110">node.js 및 npm이 컴퓨터에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-110">Requires node.js and npm on your computer.</span></span>
* <span data-ttu-id="f6c56-111">**설치 관리자** - 설치 관리자를 다운로드하여 Mac 또는 Windows에서 손쉽게 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-111">**Installer** - Download an installer for easy installation on Mac or Windows.</span></span>
* <span data-ttu-id="f6c56-112">**Docker 컨테이너** - 즉시 실행 가능한 Docker 컨테이너에서 최신 CLI를 사용하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-112">**Docker container** - Start using the latest CLI in a ready-to-run Docker container.</span></span> <span data-ttu-id="f6c56-113">Docker 호스트가 컴퓨터에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-113">Requires Docker host on your computer.</span></span>

<span data-ttu-id="f6c56-114">추가 옵션 및 배경 정보는 [GitHub](https://github.com/azure/azure-xplat-cli)에서 프로젝트 리포지토리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6c56-114">For more options and background, see the project repository on [GitHub](https://github.com/azure/azure-xplat-cli).</span></span>

<span data-ttu-id="f6c56-115">Azure CLI 1.0이 설치되면 [Azure 구독을 사용하여 연결](/cli/azure/authenticate-azure-cli)하고 명령줄 인터페이스(Bash, 터미널, 명령 프롬프트 등)에서 **azure** 명령을 실행하여 Azure 리소스 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-115">Once the Azure CLI 1.0 is installed, [connect it with your Azure subscription](/cli/azure/authenticate-azure-cli) and run the **azure** commands from your command-line interface (Bash, Terminal, Command prompt, and so on) to work with your Azure resources.</span></span>

## <a name="option-1-install-an-npm-package"></a><span data-ttu-id="f6c56-116">옵션 1: npm 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="f6c56-116">Option 1: Install an npm package</span></span>
<span data-ttu-id="f6c56-117">npm 패키지에서 CLI를 설치하려면 [최신 Node.js 및 npm](https://nodejs.org/en/download/package-manager/)을 다운로드하고 설치했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-117">To install the CLI from an npm package, make sure you have downloaded and installed the [latest Node.js and npm](https://nodejs.org/en/download/package-manager/).</span></span> <span data-ttu-id="f6c56-118">그런 다음 **npm install** azure-cli 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-118">Then, run **npm install** to install the azure-cli package:</span></span>

```bash
npm install -g azure-cli
```

<span data-ttu-id="f6c56-119">Linux 배포에서는 **npm** 명령을 정상적으로 실행하기 위해 다음과 같이 **sudo**를 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-119">On Linux distributions, you might need to use **sudo** to successfully run the **npm** command, as follows:</span></span>

```bash
sudo npm install -g azure-cli
```

> [!NOTE]
> <span data-ttu-id="f6c56-120">Linux 배포 또는 OS에 Node.js 및 npm을 설치하거나 업데이트해야 하는 경우 최신 Node.js LTS 버전(4.x)을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-120">If you need to install or update Node.js and npm on your Linux distribution or OS, we recommend that you install the most recent Node.js LTS version (4.x).</span></span> <span data-ttu-id="f6c56-121">이전 버전을 사용하는 경우 설치 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-121">If you use an older version, you might get installation errors.</span></span>

<span data-ttu-id="f6c56-122">원한다면 npm 패키지용 최신 Linux [tar 파일][linux-installer]을 로컬에 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="f6c56-122">If you prefer, download the latest Linux [tar file][linux-installer] for the npm package locally.</span></span> <span data-ttu-id="f6c56-123">그런 다음, 다운로드한 npm 패키지를 다음과 같이 설치합니다.(Linux 배포에서는 **sudo**를 사용해야 할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="f6c56-123">Then, install the downloaded npm package as follows (on Linux distributions you might need to use **sudo**):</span></span>

```bash
npm install -g <path to downloaded tar file>
```

## <a name="option-2-use-an-installer"></a><span data-ttu-id="f6c56-124">옵션 2: 설치 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="f6c56-124">Option 2: Use an installer</span></span>
<span data-ttu-id="f6c56-125">Mac 또는 Windows 컴퓨터를 사용한다면, 다음과 같은 CLI 설치 관리자를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-125">If you use a Mac or Windows computer, the following CLI installers are available for download:</span></span>

* <span data-ttu-id="f6c56-126">[Mac OS X 설치 관리자][mac-installer]</span><span class="sxs-lookup"><span data-stu-id="f6c56-126">[Mac OS X installer][mac-installer]</span></span>
* <span data-ttu-id="f6c56-127">[Windows MSI][windows-installer]</span><span class="sxs-lookup"><span data-stu-id="f6c56-127">[Windows MSI][windows-installer]</span></span>

> [!TIP]
> <span data-ttu-id="f6c56-128">Windows에서 [웹 플랫폼 설치 관리자](https://go.microsoft.com/?linkid=9828653) 를 다운로드하여 CLI를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-128">On Windows, you can also download the [Web Platform Installer](https://go.microsoft.com/?linkid=9828653) to install the CLI.</span></span> <span data-ttu-id="f6c56-129">이 설치 관리자를 사용하면 CLI를 설치한 후에 추가적인 Azure SDK 및 명령줄 도구를 설치하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-129">This installer gives you the option to install additional Azure SDK and command-line tools after installing the CLI.</span></span>

## <a name="option-3-use-a-docker-container"></a><span data-ttu-id="f6c56-130">옵션 3: Docker 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="f6c56-130">Option 3: Use a Docker container</span></span>
<span data-ttu-id="f6c56-131">컴퓨터를 [Docker](https://docs.docker.com/engine/understanding-docker/) 호스트로 설정한 경우 Docker 컨테이너에서 최신 Azure CLI 1.0을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-131">If you have set up your computer as a [Docker](https://docs.docker.com/engine/understanding-docker/) host, you can run the latest Azure CLI 1.0 in a Docker container.</span></span> <span data-ttu-id="f6c56-132">다음 명령을 실행합니다. Linux 배포에서는 **sudo**를 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-132">Run the following command (on Linux distributions you might need to use **sudo**):</span></span>

```bash
docker run -it microsoft/azure-cli
```

## <a name="run-azure-cli-10-commands"></a><span data-ttu-id="f6c56-133">Azure CLI 1.0 명령 실행</span><span class="sxs-lookup"><span data-stu-id="f6c56-133">Run Azure CLI 1.0 commands</span></span>
<span data-ttu-id="f6c56-134">Azure CLI 1.0이 설치되면 명령줄 사용자 인터페이스(Bash, 터미널, 명령 프롬프트 등)에서 **azure** 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-134">After the Azure CLI 1.0 is installed, run the **azure** command from your command-line user interface (Bash, Terminal, Command prompt, and so on).</span></span> <span data-ttu-id="f6c56-135">예를 들어 help 명령을 실행하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-135">For example, to run the help command, type the following:</span></span>

```azurecli
azure help
```

> [!NOTE]
> <span data-ttu-id="f6c56-136">일부 Linux 배포에서 `/usr/bin/env: ‘node’: No such file or directory`과 비슷한 오류가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-136">On some Linux distributions, you may receive an error similar to `/usr/bin/env: ‘node’: No such file or directory`.</span></span> <span data-ttu-id="f6c56-137">이 오류는 최근에 Node.js를 /usr/bin/nodejs에 설치할 때 비롯되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-137">This error comes from recent installations of Node.js being installed at /usr/bin/nodejs.</span></span> <span data-ttu-id="f6c56-138">해결하려면 이 명령을 실행하여 /Usr/bin/node에 바로 가기 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-138">To fix it, create a symbolic link to /usr/bin/node by running this command:</span></span>

```bash
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

<span data-ttu-id="f6c56-139">설치한 Azure CLI 1.0의 버전을 보려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-139">To see the version of the Azure CLI 1.0 you installed, type the following:</span></span>

```azurecli
azure --version
```

<span data-ttu-id="f6c56-140">이제 준비가 되었습니다!</span><span class="sxs-lookup"><span data-stu-id="f6c56-140">Now you are ready!</span></span> <span data-ttu-id="f6c56-141">사용자 고유의 리소스 작업을 수행하기 위해 모든 CLI 명령 액세스 권한을 얻으려면 [Azure CLI에서 Azure 구독에 연결](/cli/azure/authenticate-azure-cli)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-141">To access all the CLI commands to work with your own resources, [connect to your Azure subscription from the Azure CLI](/cli/azure/authenticate-azure-cli).</span></span>

> [!NOTE]
> <span data-ttu-id="f6c56-142">Azure CLI를 처음 사용할 때, 사용 정보를 Microsoft가 수집하도록 허용할 것인지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-142">When you first use Azure CLI, you see a message asking if you want to allow Microsoft to collect usage information.</span></span> <span data-ttu-id="f6c56-143">참여는 자발적입니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-143">Participation is voluntary.</span></span> <span data-ttu-id="f6c56-144">참여하기로 선택한 경우, `azure telemetry --disable`을 실행하여 언제든지 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-144">If you choose to participate, you can stop at any time by running `azure telemetry --disable`.</span></span> <span data-ttu-id="f6c56-145">언제라도 참여를 활성화하려면, `azure telemetry --enable`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-145">To enable participation at any time, run `azure telemetry --enable`.</span></span>

## <a name="update-the-cli"></a><span data-ttu-id="f6c56-146">CLI 업데이트</span><span class="sxs-lookup"><span data-stu-id="f6c56-146">Update the CLI</span></span>
<span data-ttu-id="f6c56-147">Microsoft는 업데이트된 Azure CLI 버전을 자주 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-147">Microsoft frequently releases updated versions of the Azure CLI.</span></span> <span data-ttu-id="f6c56-148">사용 중인 운영 체제에 대 한 설치 관리자를 사용하여 CLI를 다시 설치하거나 최신 Docker 컨테이너를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-148">Reinstall the CLI using the installer for your operating system, or run the latest Docker container.</span></span> <span data-ttu-id="f6c56-149">또는 최신 Node.js 및 npm이 설치된 경우 다음을 입력하여 업데이트합니다.(Linux 배포에서는 **sudo**를 사용해야 할 수 있습니다)</span><span class="sxs-lookup"><span data-stu-id="f6c56-149">Or, if you have the latest Node.js and npm installed, update by typing the following (on Linux distributions you might need to use **sudo**).</span></span>

```bash
npm update -g azure-cli
```

## <a name="enable-tab-completion"></a><span data-ttu-id="f6c56-150">탭 완성 기능 사용</span><span class="sxs-lookup"><span data-stu-id="f6c56-150">Enable tab completion</span></span>
<span data-ttu-id="f6c56-151">CLI 명령의 탭 완성 기능이 Mac 및 Linux에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-151">Tab completion of CLI commands is supported for Mac and Linux.</span></span>

<span data-ttu-id="f6c56-152">zsh에서 사용하도록 설정하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-152">To enable it in zsh, run:</span></span>

```bash
echo '. <(azure --completion)' >> .zshrc
```

<span data-ttu-id="f6c56-153">bash에서 사용하도록 설정하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-153">To enable it in bash, run:</span></span>

```bash
azure --completion >> ~/azure.completion.sh
echo 'source ~/azure.completion.sh' >> ~/.bash_profile
```


## <a name="next-steps"></a><span data-ttu-id="f6c56-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f6c56-154">Next steps</span></span>
* <span data-ttu-id="f6c56-155">[CLI에서 Azure 구독에 연결](/cli/azure/authenticate-azure-cli) 하여 Azure 리소스를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c56-155">[Connect from the CLI to your Azure subscription](/cli/azure/authenticate-azure-cli) to create and manage Azure resources.</span></span>
* <span data-ttu-id="f6c56-156">Azure CLI에 대한 자세한 내용을 보거나, 소스 코드를 다운로드하거나, 문제를 보고하거나, 프로젝트에 기여하려면 [Azure CLI에 대한 GitHub 리포지토리](https://github.com/azure/azure-xplat-cli)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="f6c56-156">To learn more about the Azure CLI, download source code, report problems, or contribute to the project, visit the [GitHub repository for the Azure CLI](https://github.com/azure/azure-xplat-cli).</span></span>
* <span data-ttu-id="f6c56-157">Azure CLI 또는 Azure 사용에 대한 질문이 있는 경우 [Azure 포럼](https://social.msdn.microsoft.com/Forums/en-US/home?forum=azurescripting)을 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="f6c56-157">If you have questions about using the Azure CLI, or Azure, visit the [Azure Forums](https://social.msdn.microsoft.com/Forums/en-US/home?forum=azurescripting).</span></span>


[mac-installer]: http://aka.ms/mac-azure-cli
[windows-installer]: http://aka.ms/webpi-azure-cli
[linux-installer]: http://aka.ms/linux-azure-cli
[cliasm]: /cli/azure/get-started-with-az-cli2
[cliarm]: ./virtual-machines/azure-cli-arm-commands.md