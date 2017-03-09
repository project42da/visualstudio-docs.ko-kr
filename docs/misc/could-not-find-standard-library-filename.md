---
title: "표준 라이브러리 &#39;&lt;filename&gt;&#39;을 찾을 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40049"
  - "bc40049"
helpviewer_keywords: 
  - "BC40049"
ms.assetid: a292f97e-4852-4021-b300-7ab47beb95d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 표준 라이브러리 &#39;&lt;filename&gt;&#39;을 찾을 수 없습니다.
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 컴파일과 연결에 필요한 표준 DLL 라이브러리 중 하나를 찾거나 열 수 없습니다.  
  
 사용할 수 없는 라이브러리는 mscorlib.dll 또는 microsoft.visualbasic.dll일 가능성이 큽니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40049  
  
### 이 오류를 해결하려면  
  
1.  오류 메시지에 언급된 파일이 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]을 실행 중인 하드 디스크에 있는지 확인합니다. 일반적으로 표준 라이브러리는 \\WINNT\\Microsoft.NET\\Framework 또는 \\WINDOWS\\Microsoft.NET\\Framework의 하위 디렉터리에 있어야 합니다.  
  
2.  파일 또는 디렉터리에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 읽기 권한을 금지하는 설정이나 특성이 없는지 확인합니다.  
  
3.  파일 이름과 확장명의 철자가 맞는지 확인합니다. 대\/소문자를 구분하지 않습니다.  
  
4.  파일이 제대로 배치되고 액세스할 수 있는 것처럼 보이면 디스크에서 손상되었을 수 있습니다. 가능한 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]을 다시 설치합니다.  
  
5.  정확한 파일 이름과 확장명을 기록한 다음 Microsoft 기술 지원 서비스에 문의하세요.  
  
## 참고 항목  
 [명령줄에서 빌드](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line)   
 [How to: Invoke the Command\-Line Compiler](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md)   
 [의견 보내기](../ide/talk-to-us.md)