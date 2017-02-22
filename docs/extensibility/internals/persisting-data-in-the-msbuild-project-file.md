---
title: "MSBuild 프로젝트 파일에 데이터를 유지 | Microsoft Docs"
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
  - "데이터를 유지 하는 프로젝트 파일"
ms.assetid: 6a920cb7-453d-4ffd-af1c-6f3084bd03f7
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# MSBuild 프로젝트 파일에 데이터를 유지
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 하위 하위 형식에 따라 데이터를 나중에 사용 하기 위해 프로젝트 파일에 유지 해야 합니다.  프로젝트 하위 프로젝트 파일 지 속성을 사용 하 여 다음 요구 사항을 충족 시키기 위해.  
  
1.  구축 프로젝트의 일부로 사용 되는 데이터를 유지 합니다.  \(Microsoft 빌드 엔진에 대 한 자세한 내용은 [MSBuild](http://msdn.microsoft.com/ko-kr/7c49aba1-ee6c-47d8-9de1-6f29a906e20b)입니다.\) 빌드에 관련 된 정보를 제출할 수 있습니다.  
  
    1.  구성에 관계 없이 데이터입니다.  비어 있거나 누락 된 조건 사용 하 여 MSBuild 요소에 저장 된 데이터입니다.  
  
    2.  구성 종속 데이터입니다.  특정 프로젝트 구성에 대 한 조건부는 MSBuild 요소에 저장 된 데이터입니다.  예를 들면 다음과 같습니다.  
  
        ```  
        <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
        ```  
  
2.  빌드에 관련 된 데이터를 유지 합니다.  XML 스키마에 대해 검증 되지 않은 자유 형태의 xml에서이 데이터를 나타낼 수 있습니다.  
  
    1.  구성에 관계 없이 데이터입니다.  
  
    2.  구성 종속 데이터입니다.  
  
## 빌드에 관련 된 정보를 유지  
 Msbuild에서 프로젝트를 빌드하는 데 유용한 데이터의 지 속성을 처리 합니다.  MSBuild 시스템 마스터 테이블 빌드 관련 정보를 유지 관리합니다.  하위 프로젝트를 get 및 set 속성 값이이 데이터에 액세스 하기 위한 담당 합니다.  또한 프로젝트 하위 유지 되어야 하는 추가 속성을 추가 하 고 지속 되지 않도록 속성을 제거 하 여 빌드에 관련 된 데이터 표에 추가할 수 있습니다.  
  
 MSBuild 데이터를 하위 프로젝트에서 기본 프로젝트 시스템을 통해 MSBuild 속성 개체를 검색 하기 위한 담당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>핵심 프로젝트 시스템 하 고 집계 프로젝트 하위 쿼리를 실행 하 여 구현 된 인터페이스는 `QueryInterface`.  
  
 다음 절차를 사용 하 여 속성을 제거 하는 단계를 설명 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>.  
  
#### MSBuild 프로젝트 파일에서 속성을 제거 하려면  
  
1.  호출 `QueryInterface` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> 의 프로젝트 하위 형식입니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.RemoveProperty%2A> 와 `pszPropName` 제거 하려면 원하는 속성을 설정 합니다.  
  
### 관련 정보를 유지 하지 않는 빌드  
 프로젝트 파일에 빌드에 문제가 되지 않습니다 데이터의 지 속성을 통해 처리 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>.  
  
 구현할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 기본 `project subtype aggregator` 개체의 `project subtype project configuration` 개체 또는 둘 모두입니다.  
  
 다음은 빌드 관련 정보를 지 속성에 대 한 기본 개념을 요약합니다.  
  
-   기본 프로젝트 로드 하 고 구성 관계 없이 데이터를 저장 하는 기본 프로젝트 하위 형식 \(바깥쪽 프로젝트 하위 형식\) 집계 개체 호출 하 고 로드 하거나 구성 종속 데이터를 저장할 프로젝트 하위 프로젝트 구성 개체를 호출 합니다.  
  
-   기본 프로젝트의 메서드를 호출 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 다중 프로젝트 하위 집계의 각 수준에 대 한 제한 시간이 및 각 수준에 대 한 GUID를 전달 합니다.  
  
-   기본 프로젝트 통과 하거나 특정 프로젝트 하위 형식에 전용으로 사용 되 고이 메커니즘을 사용 하 여 집계 수준 간에 상태를 유지 하는 방법으로는 XML 단편을 받습니다.  
  
-   기본 프로젝트에서 호출 하는 가장 바깥쪽 프로젝트 하위 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>구현에 GUID를 전달 합니다.  GUID 바깥쪽 프로젝트 하위 형식에 속하는 경우는 호출을 처리 합니다. 그렇지 않은 경우 GUID에 해당 하는 프로젝트 하위 유형의 찾을 때까지 수행 하는 내부 프로젝트 하위 형식, 통화를 위임 합니다.  
  
-   프로젝트 하위 내부 프로젝트 하위에 대 한 호출을 위임 전후 XML 조각을 수정할 수도 있습니다.  다음은 프로젝트 하위 형식에 고유한 속성을 포함 하는 파일의 이름을 해당 프로젝트 하위에 전달 되는 프로젝트 파일의 일부를 보여 줍니다.  
  
    ```  
    <ProjectExtensions>  
        <VisualStudio>  
          <FlavorProperties GUID="{<FlavorGUID>}">  
            <FlavorProject TestFileFolder="TestFile" />  
          </FlavorProperties>  
        </VisualStudio>  
      </ProjectExtensions>  
    ```  
  
## 참고 항목  
 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)