---
title: '방법: 라이브러리의 기호를 식별 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Call Browser tool, identifying symbols in the library
- Call Browser tool
ms.assetid: 8fb0de61-71e7-42d1-8b41-2ad915474384
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 310ba421120101ce545888bcf4c069ca454cf086
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-identify-symbols-in-a-library"></a>방법: 라이브러리의 기호를 식별 합니다.
기호 검색 도구 기호의 계층적 뷰를 표시합니다. 기호는 네임 스페이스, 개체, 클래스, 클래스 멤버 및 다른 언어 요소를 나타냅니다.  
  
 계층의 각 기호를 기호 라이브러리에 의해 전달 되는 탐색 정보로 식별할 수 있습니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음 인터페이스를 통해 개체 관리자:  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfoNode>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes>.  
  
 계층에 있는 기호의 위치 기호를 구분합니다. 기호 검색 도구를 특정 기호를 탐색할 수 있습니다. 기호를 고유 하 고 정규화 된 경로 위치를 결정 합니다. 경로 있는 각 요소는 노드입니다. 경로 최상위 노드로 시작 되며 특정 기호로 끝납니다. 예를 들어 M1 메서드 C1 클래스의 멤버인 경우 N1 네임 스페이스에서 c 1은 M1 방법의 전체 경로 N1 합니다. C1 합니다. M 1입니다. 이 경로는 세 개의 노드가 포함 되어: N1, c 1과 m 1입니다.  
  
 탐색 정보를 사용 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자를 찾아 선택 하 고 유지 계층에서 기호를 선택 합니다. 검색 한 도구에서 탐색 수 있습니다. 사용 하는 동안 **개체 브라우저** 의 기호를 검색 하는 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트 메서드를 마우스 오른쪽 단추로 클릭 하 고 시작할 수 있습니다는 **호출 브라우저** 메서드 호출 그래프에서 표시 하는 도구입니다.  
  
 다음 두 가지 기호 위치에 설명 합니다. 정규 형식 기호의 정규화 된 경로 기반으로 합니다. 계층 구조에서 고유한 기호 위치를 나타냅니다. 기호 검색 도구 독립적 이며 있습니다. 정규 형식 정보를 얻으려면는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 관리자 호출 개체 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> 메서드. 프레젠테이션 폼 특정 기호 검색 도구 내에서 기호 위치를 설명합니다. 기호의 위치는 hierarchicy에 다른 기호의 위치에 상대적입니다. 지정 된 기호에는 하나의 정식 경로 하지만 프레젠테이션 경로가 여러 개 있을 수 있습니다. 예를 들어, C1 클래스 C2 클래스에서 상속 하 고 두 클래스는 N1 네임 스페이스에는 **개체 브라우저** 다음 계층적 트리를 표시 합니다.  
  
```  
N1  
    C1  
        Bases and Interfaces  
            C2  
    C2  
        Bases and Interfaces  
. . . . . . . . . . .  
  
```  
  
 이 예제에서는 c 2 클래스의 정식 경로 N1 + c 2입니다. 프레젠테이션 경로의 C2 C1 및 "자료 및 인터페이스" 노드가 포함 되어: N1 + C1 + "자료 및 인터페이스" + C2 합니다.  
  
 개체 관리자 호출 프레젠테이션 폼 정보를 얻으려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> 메서드.  
  
## <a name="identifying-a-symbol-in-the-hierarchy"></a>계층 구조에서 기호를 식별합니다.  
  
#### <a name="to-obtain-canonical-and-presentation-forms-information"></a>정식 얻으려고 하 고 프레젠테이션 정보를 형성 합니다.  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> 메서드를 구현합니다.  
  
     개체 관리자 기호의 정식 경로에 포함 된 노드의 목록을 가져올 수 있는이 메서드를 호출 합니다.  
  
    ```vb  
    Public Function EnumCanonicalNodes(ByRef ppEnum As Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes) As Integer  
        Dim EnumNavInfoNodes As CallBrowserEnumNavInfoNodes = _New CallBrowserEnumNavInfoNodes(m_strMethod)  
        ppEnum = CType(EnumNavInfoNodes, IVsEnumNavInfoNodes)  
        Return 0  
    End Function  
    ```  
  
    ```csharp  
    public int EnumCanonicalNodes(out Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes ppEnum)  
    {  
        CallBrowserEnumNavInfoNodes EnumNavInfoNodes =  
            new CallBrowserEnumNavInfoNodes(m_strMethod);  
        ppEnum = (IVsEnumNavInfoNodes)(EnumNavInfoNodes);  
        return 0;  
    }  
  
    ```  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> 메서드를 구현합니다.  
  
     개체 관리자 기호의 프레젠테이션 경로에 포함 된 노드의 목록을 가져올 수이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [방법: 개체 관리자는 라이브러리를 등록 합니다.](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [방법: 라이브러리에서 제공하는 기호 목록을 개체 관리자에 노출](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)