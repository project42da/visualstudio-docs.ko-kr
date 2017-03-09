---
title: "Cannot copy multifile assembly &#39;assembly&#39; to directory &#39;directory&#39;. &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannotcopyscatterassembly"
ms.assetid: 939519c7-741d-4e05-8b63-71e39fb426ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Cannot copy multifile assembly &#39;assembly&#39; to directory &#39;directory&#39;. &lt;reason&gt;
다중 파일 어셈블리는 어셈블리가 실행될 프로젝트 디렉터리의 하위 디렉터리에 복사됩니다.  예를 들어, 출력 경로가 c:\\project1\\bin이고, a.dll과 b.dll 파일이 포함된 Test라는 어셈블리\(`CopyLocal` 속성은 `true`\)가 있으면 복사가 끝난 후 다음과 같은 파일 구조가 만들어집니다.  
  
```  
c:\project1\bin\Test  
   c:\project1\bin\Test\Test.dll   (main assembly)  
   c:\project1\bin\Test\a.dll       (file a.dll)  
   c:\project1\bin\Test\b.dll       (file b.dll)  
```  
  
 이 오류는 디스크에 c:\\project1\\bin\\Test 디렉터리를 만들 수 없을 때 표시됩니다.  
  
 이 오류는 디스크 공간이 부족하거나 경로 이름이 MAX\_PATH 한계에 이르렀음을 나타냅니다.  
  
 **이 오류를 해결하려면**  
  
-   디스크 공간을 확인하십시오.  
  
-   경로 길이가 현재 프로젝트 폴더의 경로 길이보다 짧은 다른 폴더로 프로젝트를 옮깁니다.  
  
-   절대 경로 길이가 더 짧은 다른 폴더로 출력 디렉터리를 변경합니다\(클라이언트 프로젝트의 경우에만 해당\).  
  
## 참고 항목  
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)   
 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Assemblies in the Common Language Runtime](http://msdn.microsoft.com/ko-kr/33a0bc6a-6bb3-44c7-ada7-4a046e8c0945)