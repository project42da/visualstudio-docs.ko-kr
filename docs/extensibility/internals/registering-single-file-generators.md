---
title: "단일 파일 생성기를 등록 하는 중 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "등록, 사용자 지정 도구"
  - "레지스트리 설정을 정의 하는 사용자 지정 도구"
ms.assetid: db7592c0-1273-4843-9617-6e2ddabb6ca8
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 단일 파일 생성기를 등록 하는 중
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 지정 도구에서 사용할 수 있도록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 지금 등록 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 인스턴스화할 수는 특정 프로젝트 형식에 연결 합니다.  
  
### 사용자 지정 도구를 등록 하려면  
  
1.  DLL이 사용자 지정 도구를 하거나 등록에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 로컬 레지스트리 또는 시스템 레지스트리의 HKEY\_CLASSES\_ROOT 아래에 있습니다.  
  
     예를 들어 여기서는 함께 제공 되는 관리 되는 MSDataSetGenerator 사용자 지정 도구에 대 한 등록 정보 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\CLSID\{E76D53CC-3D4F-40A2-BD4D-4F3419755476}]  
    @="COM+ class: Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"  
    "InprocServer32"="C:\\WINDOWS\\system32\\mscoree.dll"  
    "ThreadingModel"="Both"  
    "Class"="Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"  
    "Assembly"="Microsoft.VSDesigner, Version=14.0.0.0, Culture=Neutral, PublicKeyToken=b03f5f7f11d50a3a"  
    ```  
  
2.  원하는에 레지스트리 키를 만들 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Generators\\ 아래의 hive*GUID* 여기서 *GUID* 는 특정 언어의 프로젝트 시스템 또는 서비스에 의해 정의 된 GUID입니다. 키의 이름에는 사용자 지정 도구의 프로그래밍 방식으로 이름이 됩니다. 사용자 지정 도구 키에는 다음 값:  
  
    -   \(기본값\)  
  
         선택적 요소. 사용자 지정 도구에 대 한 알기 쉬운 설명을 제공합니다. 이 매개 변수는 선택 사항 이지만 권장 되는 합니다.  
  
    -   CLSID  
  
         필수 요소. COM 구성 요소를 구현 하는 클래스 라이브러리의 식별자를 지정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>합니다.  
  
    -   GeneratesDesignTimeSource  
  
         필수 요소. 이 사용자 지정 도구에서 생성 된 파일에서 형식을 사용할 수 있는 비주얼 디자이너를 숨길 있는지 여부를 나타냅니다. 이 매개 변수 값 비주얼 디자이너를 사용할 수 없는 형식에 대 한 0 \(영\) 또는 비주얼 디자이너를 사용할 수 있는 형식에 대 한 \(1\) 1 수 있어야 합니다.  
  
    > [!NOTE]
    >  사용자 지정 도구는 사용자 지정 도구 사용 가능 하도록 하려는 각 언어에 대해 별도로 등록 해야 합니다.  
  
     예를 들어는 MSDataSetGenerator 자체 등록 한 번 각 언어에 대해:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{164b10b9-b200-11d0-8c61-00a0c91e29d5}\MSDataSetGenerator]  
    @="Microsoft VB Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{fae04ec1-301f-11d3-bf4b-00c04f79efbc}\MSDataSetGenerator]  
    @="Microsoft C# Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{e6fdf8b0-f3d1-11d4-8576-0002a516ece8}\MSDataSetGenerator]  
    @="Microsoft J# Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
    ```  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>   
 [단일 파일 생성기를 구현합니다.](../../extensibility/internals/implementing-single-file-generators.md)   
 [프로젝트의 기본 네임스페이스 확인](../../misc/determining-the-default-namespace-of-a-project.md)   
 [비주얼 디자이너에 형식을 노출합니다.](../../extensibility/internals/exposing-types-to-visual-designers.md)   
 [BuildManager 개체 소개](http://msdn.microsoft.com/ko-kr/50080ec2-c1c9-412c-98ef-18d7f895e7fa)