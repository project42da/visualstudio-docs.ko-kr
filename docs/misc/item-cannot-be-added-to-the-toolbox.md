---
title: "Item cannot be added to the Toolbox. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VB_E_NOTSUPPORTEDDATA"
  - "vs.message.0x800A0065"
ms.assetid: 69fa5e73-bbc6-462c-95ca-bf2ee32d43ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Item cannot be added to the Toolbox.
이 오류는 일반적으로 도구 상자에 바로 가기 아이콘으로 표시될 수 없는 항목을 추가하려고 할 때 발생합니다.  
  
 도구 상자에 표시될 수 있는 항목은 다음과 같습니다.  
  
-   로컬 컴퓨터에 설치된 컨트롤과 .NET Framework 구성 요소  
  
 **참고** [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web forms용 컨트롤과 구성 요소는 [AspNetHostingPermission.Level 속성](https://msdn.microsoft.com/en-us/library/system.web.aspnethostingpermission.level.aspx)이 "Unlimited"여야 도구 상자에 표시될 수 있습니다.  
  
-   Visual Studio 편집기에서 끌거나 붙여넣은 선택된 텍스트\(예: 코드 조각\).  
  
 도구 상자에 표시될 수 없는 항목은 다음과 같습니다.  
  
-   Excel 통합 문서 파일  
  
-   공유 네트워크 서버에 설치된 .NET Framework 어셈블리  
  
    > [!NOTE]
    >  UNC 경로에서 추가된 어셈블리는 완전히 신뢰되지 않으므로 도구 상자에 표시될 수 있는 권한을 부여받지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  **도구 상자 사용자 지정** 대화 상자를 사용하여 로컬 컴퓨터에 설치된 컨트롤이나 구성 요소를 활성 도구 상자 탭에 추가합니다.  
  
     \-또는\-  
  
2.  선택한 텍스트를 Visual Studio 편집기에서 도구 상자로 끌거나 붙여넣습니다.  
  
## 참고 항목  
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [How to: Manipulate Toolbox Tabs](http://msdn.microsoft.com/ko-kr/21285050-cadd-455a-b1f5-a2289a89c4db)   
 [도구 상자](../ide/reference/toolbox.md)