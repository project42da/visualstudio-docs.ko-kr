---
title: "방법: 라이브러리에 대 한 기호를 식별 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "호출 브라우저 도구를 식별 하는 라이브러리의 기호"
  - "호출 브라우저 도구"
ms.assetid: 8fb0de61-71e7-42d1-8b41-2ad915474384
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 라이브러리에 대 한 기호를 식별 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 검색 도구 기호 계층 구조 보기를 표시 합니다.  기호를 네임 스페이스, 개체, 클래스, 클래스 멤버, 및 기타 언어 요소를 나타냅니다.  
  
 계층 구조에서 각 심볼 기호 라이브러리에 의해 전달 된 탐색 정보 식별할 수 있습니다의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음과 같은 인터페이스를 통해 개체 관리자:  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfoNode>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes>.  
  
 기호 계층 구조에서의 위치에 기호를 구분합니다.  이 기호 검색 도구를 특정 기호로 이동할 수 있습니다.  기호를 특수, 정규화 된 경로 위치를 결정합니다.  경로의 각 요소가 노드입니다.  경로 최상위 노드를 한 특정 기호를.  예를 들어, M1 메서드는 C1 클래스의 구성원 인 C1 N1 네임 스페이스에 있고, N1 M1 메서드의 전체 경로가입니다.C 1입니다.M1입니다.  이 경로의 세 개의 노드가 포함 되어 있습니다: C1, N1, M1 및.  
  
 탐색 정보를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 찾아 선택 하 고 유지 하는 개체 관리자 계층 구조에서 기호를 선택 합니다.  하나의 검색 도구에서 다른 위치로 이동 하 여 있습니다.  사용 하는 동안  **개체 브라우저** 기호를 찾아볼 수는 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트를 메서드를 마우스 오른쪽 단추로 클릭 하 고 시작할 수 있습니다의  **호출 브라우저** 메서드 호출 그래프를 표시 하는 도구.  
  
 두 가지 기호 위치에 설명합니다.  정규 형식에서 심볼의 정규화 된 경로 기반으로 합니다.  계층 구조에 있는 심볼의 고유한 위치를 나타냅니다.  기호 검색 도구를 독립적입니다.  정규 형식 정보를 얻을 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> 메서드.  프레젠테이션 형식 기호는 특정 기호 검색 도구 내에서 위치를 설명합니다.  심볼의 위치는 hierarchicy에서 다른 심볼의 위치에 상대적입니다.  지정 된 기호 정식 경로가 하나만 있지만 프레젠테이션 경로가 여러 개 있을 수 있습니다.  예를 들어, C1 클래스 C2 클래스에서 상속 되 고 N1 네임 스페이스의 두 클래스는 해당  **개체 브라우저** 다음과 같은 계층적 트리에 표시 됩니다.  
  
```  
N1  
    C1  
        Bases and Interfaces  
            C2  
    C2  
        Bases and Interfaces  
. . . . . . . . . . .  
  
```  
  
 이 예제에서 c 2 클래스의 정식 경로 N1 \+ c 2입니다.  프레젠테이션 경로를 C2 C1 및 "기본 및 인터페이스" 노드가 포함 되어 있습니다: N1 C2 \+ C1 \+ "기본 및 인터페이스"입니다.  
  
 개체 관리자 호출 프레젠테이션 양식 정보를 얻기 위해 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> 메서드가 있습니다.  
  
## 기호 계층 구조를 식별합니다.  
  
#### 정식 얻을 수 및 프레젠테이션 정보를 형성 합니다.  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> 메서드를 구현합니다.  
  
     개체 관리자 기호 정식 경로에 포함 된 노드 목록을 가져오려면이 메서드를 호출 합니다.  
  
    ```vb#  
    Public Function EnumCanonicalNodes(ByRef ppEnum As Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes) As Integer  
        Dim EnumNavInfoNodes As CallBrowserEnumNavInfoNodes = _New CallBrowserEnumNavInfoNodes(m_strMethod)  
        ppEnum = CType(EnumNavInfoNodes, IVsEnumNavInfoNodes)  
        Return 0  
    End Function  
    ```  
  
    ```c#  
    public int EnumCanonicalNodes(out Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes ppEnum)  
    {  
        CallBrowserEnumNavInfoNodes EnumNavInfoNodes =  
            new CallBrowserEnumNavInfoNodes(m_strMethod);  
        ppEnum = (IVsEnumNavInfoNodes)(EnumNavInfoNodes);  
        return 0;  
    }  
  
    ```  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> 메서드를 구현합니다.  
  
     개체 관리자 기호 프레젠테이션의 경로에 포함 된 노드 목록을 얻으려면이 메서드를 호출 합니다.  
  
## 참고 항목  
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [방법: 개체 관리자와 함께 라이브러리를 등록 합니다.](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [방법: 개체 관리자에는 라이브러리에서 제공 하는 기호 목록을 노출](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)