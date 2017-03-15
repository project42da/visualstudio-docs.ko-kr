---
title: "속성 창에서 필드 설명 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 창, 필드 설명"
ms.assetid: 7d92bb6a-b9b9-4cd8-99e9-b5ee129b52a3
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# 속성 창에서 필드 설명 가져오기
**속성** 창 맨 아래 설명 영역에는 선택한 속성 필드와 관련된 정보가 표시됩니다. 이 기능은 기본적으로 켜져 있습니다. 설명 필드를 숨기려면 **속성** 창을 오른쪽 단추로 클릭하고 **설명**을 클릭합니다. 그러면 메뉴 창에서 **설명** 제목 옆의 확인 표시가 사라집니다. 같은 방법으로 **설명**을 다시 토글하면 필드가 표시됩니다.  
  
 설명 필드의 정보는 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>에서 가져옵니다. 각 메서드, 인터페이스, coclass 등은 형식 라이브러리에 지역화되지 않은 `helpstring` 특성을 가질 수 있습니다.**속성** 창은 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo.GetDocumentation%2A>에서 문자열을 검색합니다.  
  
### 지역화된 도움말 문자열을 지정하려면  
  
1.  형식 라이브러리\(`typelib`\)의 라이브러리 문에 `helpstringdll` 특성을 추가합니다.  
  
    > [!NOTE]
    >  형식 라이브러리가 개체 라이브러리 \(.olb\) 파일인 경우 이 단계는 선택 사항입니다.  
  
2.  문자열에 대한 지정 `helpstringcontext` 특성을 지정합니다.`helpstring` 특성을 지정할 수도 있습니다.  
  
     이러한 특성은 실제 .chm 파일 도움말 항목에 포함된 `helpfile` 및 `helpcontext` 특성과 별개입니다.  
  
 강조 표시된 속성 이름에 대해 표시할 설명 정보를 검색하기 위해 **속성** 창이 선택된 속성에 대한 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetDocumentation2%2A>을\(를\) 호출하여 출력 문자열에 대해 원하는 `lcid` 특성을 지정합니다. 내부적으로 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2>이\(가\) `helpstringdll` 특성에 지정된 .dll 파일을 찾아서 지정된 컨텍스트 및 `lcid` 특성으로 이 .dll 파일에 대해 `DLLGetDocumentation`을\(를\) 호출합니다.  
  
 `DLLGetDocumentation`의 서명 및 구현:  
  
```  
STDAPI DLLGetDocumentation  
(  
   ITypeLib * /* ptlib */,  
   ITypeInfo * /* ptinfo */,  
   LCID /* lcid */,  
   DWORD dwCtx,  
   BSTR * pbstrHelpString  
);  
```  
  
 `DLLGetDocumentation` 함수는 DLL에 대한.def 파일에 정의된 내보내기여야 합니다.  
  
 내부적으로 .olb 파일이 생성되는데 실제로 이것은 DLL입니다. 이 DLL에는 형식 라이브러리\(.tlb\) 파일 리소스 하나와 내보내기 함수 `DLLGetDocumentation` 하나가 있습니다.  
  
 .olb 파일의 경우 .tlb 파일 자체를 포함하는 것과 같은 파일이므로 `helpstringdll` 특성은 선택 사항입니다.  
  
 따라서 **설명** 창에 문자열이 나타나도록 하려면 최소한 형식 라이브러리에서 `helpstring` 특성을 지정해야 합니다. 이러한 문자열을 지역화하려면 `helpstringdll`\(선택 사항\) 특성 및 `helpstringcontext`\(필수\) 특성을 지정하고 `DLLGetDocumentation`을\(를\) 구현해야 합니다.  
  
 idl의 `helpstringcontext` 특성 및 `DLLGetDocumentation`을\(를\) 통해 지역화된 정보를 가져올 경우 추가 인터페이스를 구현할 필요가 없습니다.  
  
 속성의 지역화된 이름 및 설명을 가져오는 또 하나의 방법은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.GetLocalizedPropertyInfo%2A> 구현입니다. 이 방법으로 구현하는 자세한 내용은 [속성 창의 필드 및 인터페이스](../extensibility/internals/properties-window-fields-and-interfaces.md)에서 참조하세요.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [속성 창의 필드 및 인터페이스](../extensibility/internals/properties-window-fields-and-interfaces.md)   
 [속성 확장](../extensibility/internals/extending-properties.md)   
 [helpstringdll](/visual-cpp/windows/helpstringdll)   
 [helpstring](/visual-cpp/windows/helpstring)   
 [helpstringcontext](/visual-cpp/windows/helpstringcontext)   
 [helpcontext](/visual-cpp/windows/helpcontext)   
 [helpfile](/visual-cpp/windows/helpfile)   
 [lcid](/visual-cpp/windows/lcid)