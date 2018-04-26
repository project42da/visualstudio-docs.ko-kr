---
title: 문제 해결 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: troubleshooting
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: b41d228bcced6149c95b09b2445dd656ed9772d6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-guide"></a>문제 해결 가이드

## <a name="error-upstream-connect-error-or-disconnectreset-before-headers"></a>오류 '업스트림 연결 오류 또는 헤더 전에 연결 끊기/다시 설정'
서비스에 액세스하려 할 때 이 오류가 표시될 수 있습니다. 예를 들어 브라우저에서 서비스의 URL로 이동할 때입니다. 

**이유:** 컨테이너 포트를 사용할 수 없습니다. 다음은 가장 일반적인 이유입니다. 
* 컨테이너가 아직 빌드 및 배포되는 중에 있습니다. `vsce up` 또는 디버거을 실행한 다음, 성공적으로 배포되기 전에 컨테이너에 액세스하려 하는 경우일 수 있습니다.
* 포트 구성은 Dockerfile, Helm 차트 및 포트를 여는 모든 서버 코드에서 일치하지 않습니다.

**try**
1. 컨테이너를 구축/배포 중인 경우 2-3초 기다렸다가 서비스에 다시 액세스해 보십시오. 
1. 포트 구성을 확인하십시오. 지정된 포트 번호는 아래 모든 자산에서 **동일**해야 합니다.
    * **Dockerfile:** `EXPOSE` 명령으로 지정됩니다.
    * **[Helm 차트](https://docs.helm.sh):** 서비스에 대한 `externalPort` 및 `internalPort` 값으로 지정(대개에 `values.yml` 파일 내에 위치),
    * 예를 들어 Node.js에서 응용 프로그램 코드에서 열리는 모든 포트: `var server = app.listen(80, function () {...}`


## <a name="config-file-not-found"></a>구성 파일을 찾을 수 없음
`vsce up`을 실행하고 다음과 같은 오류 `Config file not found: .../vsce.yaml`를 가져옵니다.

**이유:** `vsce up`은 실행하려는 코드의 루트 디렉터리에서 실행해야 하며 코드 폴더는 연결된 환경을 사용하여 실행하기 위해 초기화해야 합니다.

**try**
1. 현재 디렉터리를 서비스 코드를 포함하는 루트 폴더로 변경합니다. 
1. 코드 폴더에 vsce.yaml 파일이 없는 경우 `vsce init`을 실행하여 Docker, Kubernetes 및 VSCE 자산을 생성합니다.

## <a name="error-the-pipe-program-vsce-exited-unexpectedly-with-code-126"></a>오류: '파이프 프로그램 'vsce'가 코드 126으로 예기치 않게 종료되었습니다.'
VS Code 디버거 시작은 때때로 이 오류를 일으킬 수 있습니다. 버그입니다.

**try**
1. VS Code를 닫고 다시 엽니다.
2. 다시 F5 키를 누릅니다.


## <a name="debugging-error-configured-debug-type-coreclr-is-not-supported"></a>디버깅 오류 ‘구성된 디버그 형식 'coreclr'은 지원되지 않음’
VS Code 디버거 실행은 다음 오류를 보고합니다: `Configured debug type 'coreclr' is not supported.`

**이유:** 개발 컴퓨터에 연결된 환경에 대한 VS Code 확장이 설치되지 않았습니다.

**Try:** [연결된 환경에 대한 VS 코드 확장](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code)을 설치합니다.


## <a name="the-azure-portal-doesnt-show-connected-environment-instances"></a>Azure 포털은 연결된 환경 인스턴스를 표시하지 않음

**이유:** 연결된 환경에 대한 Azure 포털 경험은 아직 미리 보기가 준비되지 않았습니다.


## <a name="the-type-or-namespace-name-mylibrary-could-not-be-found"></a>형식 또는 네임스페이스 이름 'MyLibrary'를 찾을 수 없음

**이유:** 빌드 컨텍스트가 기본적으로 프로젝트/서비스 수준에 있으므로 사용하는 라이브러리 프로젝트를 찾을 수 없습니다.

**Try:** 수행해야 하는 작업은 무엇인가요?
1. 빌드 컨텍스트를 솔루션 수준으로 설정하려면 vsce.yaml 파일을 수정합니다.
2. 새 빌드 컨텍스트를 기준으로 제대로 csproj 파일을 참조하려면 Dockerfile 및 Dockerfile.develop 파일을 수정합니다.
3. .dockerignore 파일을 .sln 파일 옆에 배치하고 필요에 따라 수정합니다.

https://github.com/sgreenmsft/buildcontextsample에서 예제를 찾을 수 있음

## <a name="microsoftconnectedenvironmentregisteraction-authorization-error-when-creating-an-environment"></a>환경을 만들 경우 'Microsoft.ConnectedEnvironment/register/action' 권한 부여 오류
환경을 관리하고 소유자 또는 참가자 액세스 권한이 없는 Azure 구독에서 작업하는 경우 다음과 같은 오류가 표시될 수 있습니다.
`The client '<User email/Id>' with object id '<Guid>' does not have authorization to perform action 'Microsoft.ConnectedEnvironment/register/action' over scope '/subscriptions/<Subscription Id>'.`

**이유:** 선택한 Azure 구독이 Microsoft.ConnectedEnvironment 네임스페이스를 등록하지 않았습니다.

**Try:** Azure 구독에 소유자 또는 참가자 액세스 권한이 있는 사용자가 Microsoft.ConnectedEnvironment를 수동으로 등록하기 위한 다음의 Azure CLI 명령을 실행할 수 있습니다.

```cmd
az provider register --namespace Microsoft.ConnectedEnvironment
```

## <a name="vsce-doesnt-seem-to-use-my-existing-dockerfile-to-build-a-container"></a>VSCE는 나의 기존 Dockerfile을 사용하여 컨테이너를 빌드하지 않는 것 같음 

**이유:** VSCE가 프로젝트에서 특정 Dockerfile을 가리키도록 구성될 수 있습니다. VSCE가 컨테이너를 빌드할 것으로 예상하는 Dockerfile를 사용하지 않는 것 같은 경우 VSCE에 그 위치를 명시적으로 밝혀야 합니다. 

**Try:** 프로젝트에서 VSCE에서 생성한 `vsce.yaml`파일을 엽니다. `configurations->develop->build->dockerfile` 지시문을 사용하여 사용하려는 Dockerfile을 가리킵니다.

```
...
configurations:
  develop:
    build:
      dockerfile: Dockerfile.develop
```