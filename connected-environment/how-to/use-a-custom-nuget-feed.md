---
title: 연결된 환경에서 사용자 지정 NuGet 피드를 사용하는 방법 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 03/27/2018
ms.topic: conceptual
description: 사용자 지정 NuGet 피드를 사용하여 연결된 환경에서 NuGet 패키지에 액세스하고 사용합니다.
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 1c4c0c53b81f29436bb7110395981071411fd6b2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
#  <a name="use-a-custom-nuget-feed-in-a-connected-environment"></a>연결된 환경에서 사용자 지정 NuGet 피드 사용

NuGet 피드는 프로젝트에서 패키지 원본을 포함하는 편리한 방법을 제공합니다. 연결된 환경은 종속성을 Docker 컨테이너에 제대로 설치하기 위해 이 피드에 액세스할 수 있어야 합니다.

NuGet 피드를 설정하려면:
1. `PackageReference` 노드 아래의 `*.csproj` 파일에서 [패키지 참조](https://docs.microsoft.com/en-us/nuget/consume-packages/package-references-in-project-files)를 추가합니다.

   ```xml
   <ItemGroup>
       <!-- ... -->
       <PackageReference Include="Contoso.Utility.UsefulStuff" Version="3.6.0" />
       <!-- ... -->
   </ItemGroup>
   ```

2. 프로젝트 폴더에서 [NuGet.Config](https://docs.microsoft.com/en-us/nuget/reference/nuget-config-file) 파일을 만듭니다.
     * NuGet 피드 위치를 참조하는 `packageSources` 섹션을 사용합니다. 중요: NuGet 피드에 공개적으로 액세스 가능해야 합니다.
     * 사용자 이름 및 암호 자격 증명을 구성하는 `packageSourceCredentials` 섹션을 사용합니다. 

   ```xml
   <packageSources>
       <add key="Contoso" value="https://contoso.com/packages/" />
   </packageSources>

   <packageSourceCredentials>
       <Contoso>
           <add key="Username" value="user@contoso.com" />
           <add key="ClearTextPassword" value="33f!!lloppa" />
       </Contoso>
   </packageSourceCredentials>
   ```

3. 원본 코드 제어를 사용하는 경우:
    - 원본 리포지토리에 자격 증명을 실수로 커밋하지 않도록 `.gitignore` 파일에서 `NuGet.Config`를 참조합니다.
    - 프로젝트에서 `vsce.yaml` 파일을 열고, `build` 섹션을 찾고, 다음 코드 조각을 삽입하여 `NuGet.Config` 파일을 컨테이너 이미지 빌드 프로세스 중에 사용될 수 있도록 Azure에 동기화해야 합니다. (기본적으로 연결된 환경은 `.gitignore` 및 `.dockerignore` 규칙과 일치하는 파일을 동기화하지 않습니다.)

        ```yaml
        build:
        useGitIgnore: true
        ignore:
        - “!NuGet.Config”
        ```


## <a name="next-steps"></a>다음 단계

위의 단계를 완료하게 되면 다음에 `vsce up`을 실행(또는 VSCode 또는 Visual Studio에서 `F5`를 누름)할 때 연결된 환경은 `NuGet.Config` 파일을 Azure에 동기화합니다. 그러면 `dotnet restore`에서 활용하여 컨테이너에에서 패키지 종속성을 설치합니다.

