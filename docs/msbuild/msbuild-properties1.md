---
title: "MSBuild Properties1 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild 속성"
ms.assetid: 962912ac-8931-49bf-a88c-0200b6e37362
caps.latest.revision: 32
caps.handback.revision: 32
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild Properties1
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

속성은 빌드를 구성 하는 데 사용할 수 있는 이름-값 쌍입니다. 속성은 조건을 평가 하 고 프로젝트 파일 전체에서 참조 되는 값을 저장 작업에 대 한 값을 전달 하는 데 유용 합니다.  
  
## <a name="defining-and-referencing-properties-in-a-project-file"></a>프로젝트 파일에서 속성 정의 및 참조  
 자식으로 속성의 이름을 가진 요소를 만들어 속성이 선언 되는 [PropertyGroup](../msbuild/propertygroup-element-msbuild.md) 요소입니다. 예를 들어, 다음 XML 이라는 속성을 만듭니다 `BuildDir` 값이 있는 `Build`합니다.  
  
```  
<PropertyGroup>  
    <BuildDir>Build</BuildDir>  
</PropertyGroup>  
```  
  
 속성은 프로젝트 파일 전체에서 $ 구문을 사용 하 여 참조 됩니다 (`PropertyName`). 예를 들어 이전 예제의 속성은 $(BuildDir)를 사용 하 여 참조 됩니다.  
  
 속성을 재정의 하 여 속성 값을 변경할 수 있습니다.  `BuildDir` 속성이이 XML을 사용 하 여 새 값을 지정할 수 있습니다.  
  
```  
<PropertyGroup>  
    <BuildDir>Alternate</BuildDir>  
</PropertyGroup>  
```  
  
 속성은 프로젝트 파일에 표시 된 순서 대로 평가 됩니다. 에 대 한 새 값 `BuildDir` 이전 값을 할당 한 후에 선언 되어야 합니다.  
  
## <a name="reserved-properties"></a>예약 된 속성  
 MSBuild는 몇 개의 속성 이름을 예약하여 프로젝트 파일과 MSBuild 이진 파일에 대한 정보를 저장합니다. 이러한 속성은 다른 속성과 마찬가지로 $ 표기법을 사용 하 여 참조 됩니다. 예를 들어 $(MSBuildProjectFile) 파일 이름 확장명을 포함 하는 프로젝트 파일의 전체 파일 이름을 반환 합니다.  
  
 자세한 내용은 참조 [하는 방법: 이름 또는 프로젝트 파일의 위치 참조](../Topic/How%20to:%20Reference%20the%20Name%20or%20Location%20of%20the%20Project%20File.md) 및 [MSBuild 예약 및 잘 알려진 속성](../msbuild/msbuild-reserved-and-well-known-properties.md)합니다.  
  
## <a name="environment-properties"></a>환경 속성  
 예약 된 속성을 참조 하는 것 처럼 프로젝트 파일에서 환경 변수를 참조할 수 있습니다. 예를 들어, 사용 하는 `PATH` 프로젝트 파일을 사용 하 여 $(Path)에 대 한 환경 변수입니다. 환경 속성과 동일한 이름을 가진 속성 정의 포함 하는 프로젝트를 프로젝트의 속성이 환경 변수의 값 보다 우선 합니다.  
  
 각 MSBuild 프로젝트에는 격리된 환경 블록을 가지고 있습니다. 오직 읽거나 자체 블록에 기록만 합니다.  MSBuild는 프로젝트 파일을 평가하거나 빌드하기 전에 속성 컬렉션을 초기화하는 경우에만 환경 변수를 읽습니다. 그 후 환경 속성은 고정됩니다. 즉, 각 생성된 도구가 같은 이름과 값으로 시작합니다.  
  
 생성 된 도구 내에서 환경 변수의 현재 값을 사용은 [속성 함수](../msbuild/property-functions.md) System.Environment.GetEnvironmentVariable 합니다. 그러나 작업 매개 변수를 사용 하 여 것이 좋습니다, <xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A>합니다. 이 문자열 배열에 설정된 환경 속성은 시스템 환경 변수에 영향을 주지 않고 생성된 도구에 전달할 수 있습니다.  
  
> [!TIP]
>  모든 환경 변수가 읽어들여져 초기 속성이 되는 것은 아닙니다. "386" 같은 유효한 MSBuild 속성 이름이 아닌 모든 환경 변수는 무시됩니다.  
  
 자세한 내용은 참조 [하는 방법: 빌드 시에서 환경 변수를 사용 하 여](../Topic/How%20to:%20Use%20Environment%20Variables%20in%20a%20Build.md)합니다.  
  
## <a name="registry-properties"></a>레지스트리 속성  
 다음 구문을 사용 하 여 시스템 레지스트리 값을 읽을 수 있습니다 여기서 `Hive` (예: HKEY_LOCAL_MACHINE), 레지스트리 하이브입니다 `Key` 키 이름인 `SubKey` 하위 키 이름 및 `Value` 하위 키의 값입니다.  
  
```  
$(registry:Hive\MyKey\MySubKey@Value)  
```  
  
 기본 하위 키 값을 가져오려면 생략 된 `Value`합니다.  
  
```  
$(registry:Hive\MyKey\MySubKey)  
```  
  
 빌드 속성을 초기화 하려면이 레지스트리 값을 사용할 수 있습니다. 예를 들어 Visual Studio 웹 브라우저 홈 페이지를 나타내는 빌드 속성을 만들려면이 코드를 사용 합니다.  
  
```  
<PropertyGroup>  
  <VisualStudioWebBrowserHomePage>  
    $(registry:HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\12.0\WebBrowser@HomePage)  
  </VisualStudioWebBrowserHomePage>  
<PropertyGroup>  
```  
  
## <a name="global-properties"></a>전역 속성  
 MSBuild를 사용 하는 명령줄에서 사용 하 여 속성을 설정할 수 있습니다.는 **/property** (또는 **/p**) 전환 합니다. 이러한 전역 속성 값은 프로젝트 파일에 설정 된 속성 값을 재정의 합니다. 이 환경 속성을 포함 하지만 변경할 수 없는 예약 된 속성을 포함 하지 않습니다.  
  
 다음 예제에서는 전역 설정 `Configuration` 속성을 `DEBUG`합니다.  
  
```  
msbuild.exe MyProj.proj /p:Configuration=DEBUG  
```  
  
 전역 속성을 설정 하거나 사용 하 여 다중 프로젝트의 자식 프로젝트에 대 한 수정도 수는 `Properties` MSBuild 작업의 특성입니다. 자세한 내용은 참조 [MSBuild 작업](../msbuild/msbuild-task.md)합니다.  
  
 프로젝트 태그에 `TreatAsLocalProperty` 특성을 사용하여 속성을 지정할 경우, 해당 전역 속성 값은 프로젝트 파일에 설정된 속성 값을 재정의하지 않습니다. 자세한 내용은 참조 [프로젝트 요소 (MSBuild)](../msbuild/project-element-msbuild.md) 및 [하는 방법: 동일한 소스 파일 다양 한 옵션으로 빌드](../msbuild/how-to-build-the-same-source-files-with-different-options.md)합니다.  
  
## <a name="property-functions"></a>속성 함수  
 .NET Framework 버전 4부터는 속성 함수를 사용하여 MSBuild 스크립트를 평가할 수 있습니다. 시스템 시간을 읽고 문자열을 비교 및 정규식을 일치 시키고 MSBuild 작업을 사용 하지 않고 빌드 스크립트 내에서 다른 많은 작업을 수행할 수 있습니다.  
  
 문자열 (인스턴스) 메서드를 사용 하 여 모든 속성 값에 작동 하 고 많은 시스템 클래스의 정적 메서드를 호출할 수 있습니다. 예를 들어 다음과 같은 오늘 날짜에 빌드 속성을 설정할 수 있습니다.  
  
```  
<Today>$([System.DateTime]::Now.ToString("yyyy.MM.dd"))</Today>  
```  
  
 자세한 내용 및 속성 함수 목록에 대 한 참조 [속성 함수](../msbuild/property-functions.md)합니다.  
  
## <a name="creating-properties-during-execution"></a>실행 중에 속성 만들기  
 속성의 바깥쪽으로 배치 `Target` 빌드의 평가 단계에서 요소 값이 할당 됩니다. 후속 실행 단계에서 속성을 만들거나 다음과 같이 수정 합니다.  
  
-   임의의 작업에서 속성을 내보낼 수 있습니다. 내보낼 속성을는 [작업](../msbuild/task-element-msbuild.md) 요소에 자식이 있어야 [출력](../msbuild/output-element-msbuild.md) 있는 요소는 `PropertyName` 특성입니다.  
  
-   속성에서 내보낼 수 있습니다는 [CreateProperty](../msbuild/createproperty-task.md) 작업입니다. 이 사용법은 사용 되지 않습니다.  
  
-   .NET Framework 3.5 부터는 `Target` 요소가 포함 될 수 있습니다 `PropertyGroup` 속성 선언을 포함할 수 있는 요소입니다.  
  
## <a name="storing-xml-in-properties"></a>속성에 XML을 저장합니다.  
 속성 값을 작업으로 전달 하거나 로깅 정보를 표시에 도움이 될 수 있는 임의의 XML을 포함할 수 있습니다. 다음 예제는 `ConfigTemplate` XML 및 기타 속성을 포함 하는 값 속성을 참조 합니다. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 해당 속성 값을 사용 하 여 속성 참조를 대체 합니다. 속성 값이 나타나는 순서 대로 할당 됩니다. 따라서이 예제에서에서 `$(MySupportedVersion)`, `$(MyRequiredVersion)`, 및 `$(MySafeMode)` 이미 정의 되어 해야 합니다.  
  
```  
  
<PropertyGroup>  
    <ConfigTemplate>  
        <Configuration>  
            <Startup>  
                <SupportedRuntime  
                    ImageVersion="$(MySupportedVersion)"  
                    Version="$(MySupportedVersion)"/>  
                <RequiredRuntime  
                    ImageVersion="$(MyRequiredVersion)  
                    Version="$(MyRequiredVersion)"  
                    SafeMode="$(MySafeMode)"/>  
            </Startup>  
        </Configuration>  
    </ConfigTemplate>  
</PropertyGroup>  
```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)  
 [MSBuild](../msbuild/msbuild1.md)  
 [방법: 빌드 시에서 환경 변수 사용](../Topic/How%20to:%20Use%20Environment%20Variables%20in%20a%20Build.md)   
 [방법: 이름 또는 프로젝트 파일의 위치 참조](../Topic/How%20to:%20Reference%20the%20Name%20or%20Location%20of%20the%20Project%20File.md)   
 [방법: 다양 한 옵션으로 동일한 소스 파일 빌드](../msbuild/how-to-build-the-same-source-files-with-different-options.md)   
 [MSBuild 예약 및 잘 알려진 속성](../msbuild/msbuild-reserved-and-well-known-properties.md)   
 [Property 요소 (MSBuild)](../msbuild/property-element-msbuild.md)