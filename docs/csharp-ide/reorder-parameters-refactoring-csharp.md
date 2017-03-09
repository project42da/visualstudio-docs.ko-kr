---
title: "Reorder Parameters Refactoring (C#) | Microsoft Docs"
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
  - "vs.csharp.refactoring.reorder"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "refactoring [C#], Reorder Parameters"
  - "Reorder Parameters refactoring [C#]"
ms.assetid: 4dabf21a-a9f0-41e9-b11b-55760cf2bd90
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Reorder Parameters Refactoring (C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`Reorder Parameters`는 메서드, 인덱스 및 대리자에 대한 매개 변수의 순서를 변경하는 간편한 방법을 제공하는 Visual C\# 리팩터링 작업입니다.  `Reorder Parameters`가 선언을 변경하면 멤버가 호출되는 모든 곳에서 매개 변수는 새 순서를 반영하도록 다시 정렬됩니다.  
  
 `Reorder Parameters` 작업을 수행하려면 커서를 메서드, 인덱서 또는 대리자 위나 바로 다음에 놓습니다.  커서가 해당 위치에 있을 때 바로 가기 키를 누르거나 바로 가기 메뉴에서 명령을 선택하여 `Reorder Parameters` 작업을 호출합니다.  
  
> [!NOTE]
>  확장 메서드에서 첫 번째 매개 변수를 다시 정렬할 수 없습니다.  
  
### 매개 변수를 다시 정렬하려면  
  
1.  `ReorderParameters`라는 클래스 라이브러리를 만든 다음 `Class1`을 다음 예제 코드로 바꿉니다.  
  
    ```c#  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  커서를 메서드 선언이나 메서드 호출에 있는 `MethodB`에 놓습니다.  
  
3.  **리팩터링** 메뉴에서 **매개 변수 다시 정렬**을 클릭합니다.  
  
     **매개 변수 다시 정렬** 대화 상자가 표시됩니다.  
  
4.  **매개 변수 다시 정렬** 대화 상자의 **매개 변수** 목록에서 `int i`를 선택한 다음 아래쪽 화살표를 클릭합니다.  
  
     **매개 변수** 목록에서 `bool b` 다음에 `int i`를 끌어 올 수도 있습니다.  
  
5.  **매개 변수 다시 정렬** 대화 상자에서 **확인**을 클릭합니다.  
  
     **매개 변수 다시 정렬** 대화 상자에서 **참조 변경 내용 미리 보기** 옵션이 선택되었으면 **변경 내용 미리 보기 \- 매개 변수 다시 정렬** 대화 상자가 나타납니다.  시그니처와 메서드 호출 모두에 있는 `MethodB`의 매개 변수 목록에서 변경 내용을 미리 볼 수 있습니다.  
  
    1.  **변경 내용 미리 보기 — 매개 변수 다시 정렬** 대화 상자가 나타나면 **적용**을 클릭합니다.  
  
         이 예제에서는 `MethodB`에 대한 메서드 선언과 모든 메서드 호출 사이트가 업데이트됩니다.  
  
## 설명  
 메서드 선언이나 메서드 호출에서 매개 변수를 다시 정렬할 수 있습니다.  커서를 메서드나 대리자 선언 위나 바로 다음에 놓고 본문에 놓지는 마십시오.  
  
## 참고 항목  
 [Refactoring \(C\#\)](../csharp-ide/refactoring-csharp.md)