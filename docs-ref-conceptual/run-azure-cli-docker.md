---
title: "Docker 컨테이너에서 Azure CLI 2.0 실행"
description: "Azure CLI 2.0을 호스팅하는 Docker 컨테이너 실행 방법"
keywords: "Azure CLI,Azure CLI 설치,azure docker,azure docker 이미지,"
author: sptramer
ms.author: sttramer
manager: routlaw
ms.date: 01/29/18
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: azurecli
ms.service: multiple
ms.openlocfilehash: 819ff0cdb0df6057a5dff8f8ab015796f06c6a9b
ms.sourcegitcommit: 8606f36963e8daa6448d637393d1e4ef2c9859a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="run-azure-cli-20-in-a-docker-container"></a><span data-ttu-id="5e6c0-104">Docker 컨테이너에서 Azure CLI 2.0 실행</span><span class="sxs-lookup"><span data-stu-id="5e6c0-104">Run Azure CLI 2.0 in a Docker container</span></span>

<span data-ttu-id="5e6c0-105">Docker를 사용하여 Azure CLI 2.0이 사전 설치된 독립 실행형 Linux 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-105">You can use Docker to run a standalone Linux container with the Azure CLI 2.0 pre-installed.</span></span> <span data-ttu-id="5e6c0-106">Docker는 CLI를 사용해보고 자신에게 적합한지 확인할 수 있는 환경을 신속하게 시작하거나, 우리 이미지를 자신의 배포를 위한 기본으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-106">Docker lets you get started quickly with an environment where you can try out the CLI to decide if it's right for you, or use our image as a base for your own deployment.</span></span>

## <a name="run-in-a-docker-container"></a><span data-ttu-id="5e6c0-107">Docker 컨테이너에서 실행</span><span class="sxs-lookup"><span data-stu-id="5e6c0-107">Run in a Docker container</span></span>

<span data-ttu-id="5e6c0-108">`docker run`을 사용하여 CLI를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-108">Install the CLI using `docker run`.</span></span>

   ```bash
   docker run -it microsoft/azure-cli
   ```

<span data-ttu-id="5e6c0-109">CLI는 `/usr/local/bin`에 있는 `az` 명령으로 이미지에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-109">The CLI is installed on the image as the `az` command in `/usr/local/bin`.</span></span>

> [!NOTE]
> <span data-ttu-id="5e6c0-110">사용자 환경에서 SSH 키를 선택하려는 경우 `-v ${HOME}:/root`를 사용하여 $HOME을 `/root`로 탑재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-110">If you want to pick up the SSH keys from your user environment, you can use `-v ${HOME}:/root` to mount $HOME as `/root`.</span></span>

> ```bash
> docker run -it -v ${HOME}:/root microsoft/azure-cli
> ```

## <a name="update-docker-image"></a><span data-ttu-id="5e6c0-111">Docker 이미지 업데이트</span><span class="sxs-lookup"><span data-stu-id="5e6c0-111">Update Docker image</span></span>

<span data-ttu-id="5e6c0-112">Docker를 사용하여 업데이트하려면 새 이미지를 풀링하고 모든 기존 컨테이너를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-112">Updating with Docker requires both pulling the new image and re-creating any existing containers.</span></span> <span data-ttu-id="5e6c0-113">이러한 이유로 CLI를 데이터 저장소로 호스트하는 컨테이너를 사용하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-113">For this reason you should try to avoid using a container that hosts the CLI as a data store.</span></span>

<span data-ttu-id="5e6c0-114">`docker pull`을 사용하여 로컬 이미지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-114">Update your local image with `docker pull`.</span></span>

```bash
docker pull microsoft/azure-cli
```

## <a name="uninstall-docker-image"></a><span data-ttu-id="5e6c0-115">Docker 이미지 제거</span><span class="sxs-lookup"><span data-stu-id="5e6c0-115">Uninstall Docker image</span></span>

[!INCLUDE [uninstall-boilerplate.md](includes/uninstall-boilerplate.md)]

<span data-ttu-id="5e6c0-116">CLI 이미지를 실행하는 모든 컨테이너를 중지한 후 이미지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6c0-116">After halting any containers running the CLI image, remove it.</span></span>

```bash
docker rmi microsoft/azure-cli
```