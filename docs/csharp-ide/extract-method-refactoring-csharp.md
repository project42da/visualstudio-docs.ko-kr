---
title: "메서드 추출 리팩터링(C#) | Microsoft Docs"
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
  - "vs.csharp.refactoring.extractmethod"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "리팩터링[C#], 메서드 추출"
  - "메서드 추출 리팩터링 작업[C#]"
ms.assetid: eeba11df-a815-4bec-9c21-8a831891b783
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 메서드 추출 리팩터링(C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**메서드 추출**은 기존 멤버의 코드 조각으로부터 새 메서드를 간편하게 만드는 방법을 제공하는 리팩터링 작업입니다.  
  
 **메서드 추출**을 사용하면 기존 멤버의 코드 블록에서 선택된 코드를 추출하여 새 메서드를 만들 수 있습니다.  새로 추출된 메서드에는 선택된 코드가 포함되고, 기존 멤버의 선택된 코드는 새 메서드에 대한 호출로 바뀝니다.  코드 조각을 별도의 자체 메서드로 변환하면 코드를 빠르게 정확하게 다시 구성하여 재사용률과 가독성을 높일 수 있습니다.  
  
 **메서드 추출**을 사용하면 다음과 같은 이점이 있습니다.  
  
-   다시 사용할 수 있는 별도의 메서드를 중요시하여 좋은 코딩 습관을 갖게 합니다.  
  
-   좋은 구성을 통해 자체적으로 설명하는 코드를 작성할 수 있습니다.  
  
     서술적 이름을 사용하면 일련의 주석을 읽는 것처럼 메서드의 가독성을 높일 수 있습니다.  
  
-   더욱 세분화된 메서드를 만들어 재정의를 단순화할 수 있습니다.  
  
-   코드 중복을 줄입니다.  
  
### 메서드 추출을 사용하려면  
  
1.  `ExtractMethod`라는 콘솔 응용 프로그램을 만든 다음 `Program`을 다음 예제 코드로 바꿉니다.  
  
    ```c#  
    class A  
    {  
        const double PI = 3.141592;  
  
        double CalculatePaintNeeded(double paintPerUnit, double radius)  
        {  
            // Select any of the following:  
            // 1. The entire next line of code.  
            // 2. The right-hand side of the next line of code.  
            // 3. Just "PI *" of the right-hand side of the next line  
            //    of code (to see the prompt for selection expansion).  
            // 4.  All code within the method body.  
            // ...Then invoke Extract Method.  
  
            double area = PI * radius * radius;  
  
            return area / paintPerUnit;  
        }  
    }  
    ```  
  
2.  추출할 코드 조각을 선택합니다.  
  
    ```c#  
    double area = PI * radius * radius;  
  
    ```  
  
3.  **리팩터링** 메뉴에서 **메서드 추출**을 클릭합니다.  
  
     **메서드 추출** 대화 상자가 나타납니다.  
  
     바로 가기 키 Ctrl\+R, M을 입력해도 **메서드 추출** 대화 상자가 표시됩니다.  
  
     선택한 코드를 마우스 오른쪽 단추로 클릭하고 **리팩터링**을 가리킨 다음 **메서드 추출**을 클릭하여 **메서드 추출** 대화 상자를 표시할 수도 있습니다.  
  
4.  **새 메서드 이름** 상자에 새 메서드 이름을 지정합니다\(예: `CircleArea`\).  
  
     **메서드 시그니처 미리 보기**에 새 메서드 시그니처의 미리 보기가 표시됩니다. .  
  
5.  **확인**을 클릭합니다.  
  
## 설명  
 **메서드 추출** 명령을 사용하면 새 메서드는 같은 클래스의 소스 멤버 뒤에 삽입됩니다.  
  
## 부분 형식\(Partial type\)  
 클래스가 부분 형식인 경우 **메서드 추출**을 사용하면 소스 멤버 바로 뒤에 새 메서드가 생성됩니다.  **메서드 추출**에서 새 메서드의 시그니처를 결정하며, 새 메서드의 코드에서 어떠한 인스턴스 데이터도 참조하지 않는 경우 static 메서드를 만듭니다.  
  
## 제네릭 형식 매개 변수  
 제약이 없는 제네릭 형식 매개 변수를 사용하는 메서드를 추출할 때는 해당 매개 변수에 값이 할당되지 않는 한 생성되는 코드에서 매개 변수에 `ref` 한정자가 추가되지 않습니다.  추출된 메서드가 참조 형식을 제네릭 형식 인수로 지원할 경우 메서드 시그니처의 매개 변수에 수동으로 `ref` 한정자를 추가해야 합니다.  
  
## 익명 메서드  
 익명 메서드 외부에서 선언되거나 참조되는 지역 변수에 대한 참조를 포함하는 익명 메서드의 일부를 추출하면 의미 체계가 변경될 수 있다는 경고 메시지가 표시됩니다.  
  
 익명 메서드가 지역 변수의 값을 사용하면 이 값은 익명 메서드가 실행되는 순간에 가져옵니다.  익명 메서드가 다른 메서드에서 추출되는 경우 지역 변수의 값은 추출된 메서드를 호출하는 순간 가져옵니다.  
  
 다음 예제에서는 이러한 의미 변화를 보여 줍니다.  이 코드가 실행될 경우 **11**이 콘솔에 인쇄됩니다.  **메서드 추출**을 사용하여 코드 주석으로 표시된 코드 영역을 자체 메서드로 추출한 다음 리팩터링된 코드를 실행하면 콘솔에 **10**이 출력됩니다.  
  
```c#  
class Program  
{  
    delegate void D();  
    D d;  
    static void Main(string[] args)  
    {  
        Program p = new Program();  
        int i = 10;  
        /*begin extraction*/  
            p.d = delegate { Console.WriteLine(i++); };  
        /*end extraction*/  
        i++;  
        p.d();  
    }  
}  
```  
  
 이 문제를 피하려면 익명 메서드에서 사용되는 지역 변수를 클래스의 필드로 만듭니다.  
  
## 참고 항목  
 [Refactoring \(C\#\)](../csharp-ide/refactoring-csharp.md)