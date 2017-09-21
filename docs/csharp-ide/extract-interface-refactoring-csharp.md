---
title: "Extract Interface Refactoring (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.csharp.refactoring.extractinterface"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "refactoring [C#], Extract Interface"
  - "Extract Interface refactoring operation [C#]"
ms.assetid: 7d0aa225-3b33-4331-9652-5a67cac6f3d0
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Extract Interface Refactoring (C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

인터페이스 추출은 기존 클래스, 구조체 또는 인터페이스에서 발생한 멤버를 사용하여 새 인터페이스를 간편하게 만드는 방법을 제공하는 리팩터링 작업입니다.  
  
 여러 클라이언트에서 클래스, 구조체 또는 인터페이스에 있는 멤버의 동일한 하위 집합을 사용하거나 여러 클래스, 구조체 또는 인터페이스가 공통으로 멤버의 하위 집합을 가지는 경우 멤버의 하위 집합을 인터페이스로 구현하면 유용할 수 있습니다.  인터페이스 사용에 대한 자세한 내용은 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)를 참조하십시오.  
  
 인터페이스 추출은 새 파일에 인터페이스를 생성하고 커서를 새 파일의 시작 부분에 둡니다.  **인터페이스 추출** 대화 상자를 사용하여 새 인터페이스로 추출할 멤버, 새 인터페이스 이름 및 생성되는 파일의 이름을 지정할 수 있습니다.  
  
### 인터페이스 추출을 사용하려면  
  
1.  `ExtractInterface`라는 콘솔 응용 프로그램을 만들고 `Program`을 다음 코드로 바꿉니다.  
  
    ```c#  
    // Invoke Extract Interface on ProtoA.  
    // Note:  the extracted interface will be created in a new file.  
    class ProtoA  
    {  
        public void MethodB(string s) { }  
    }  
    ```  
  
2.  커서를 `MethodB`에 놓고 **리팩터링** 메뉴에서 **인터페이스 추출**을 클릭합니다.  
  
     **인터페이스 추출** 대화 상자가 나타납니다.  
  
     바로 가기 키 Ctrl\+R, I를 입력해도 **인터페이스 추출** 대화 상자가 표시됩니다.  
  
     마우스 오른쪽 단추로 클릭하고 **리팩터링**을 가리킨 다음 **인터페이스 추출**을 클릭하여 **인터페이스 추출** 대화 상자를 표시할 수도 있습니다.  
  
3.  **모두 선택**을 클릭합니다.  
  
4.  **확인**을 클릭합니다.  
  
     IProtoA.cs라는 새 파일과 다음 코드가 표시됩니다.  
  
    ```c#  
    using System;  
    namespace TopThreeRefactorings  
    {  
        interface IProtoA  
        {  
            void MethodB(string s);  
        }  
    }  
    ```  
  
## 설명  
 추출할 멤버를 포함하는 클래스, 구조체 또는 인터페이스에 커서가 있을 때만 이 기능에 액세스할 수 있습니다.  커서가 이 위치에 있을 때 인터페이스 추출 리팩터링 작업을 호출합니다.  
  
 클래스 또는 구조체에 대해 인터페이스 추출을 호출하면 기본 및 인터페이스 목록이 새 인터페이스 이름을 포함하도록 수정됩니다.  인터페이스에 대해 인터페이스 추출을 호출하면 기본 및 인터페이스 목록은 수정되지 않습니다.  
  
## 참고 항목  
 [Refactoring \(C\#\)](../csharp-ide/refactoring-csharp.md)