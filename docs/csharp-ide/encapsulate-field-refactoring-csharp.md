---
redirect_url: /visualstudio/csharp-ide/refactoring/encapsulate-field
title: "필드 캡슐화 리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- Encapsulate Field refactoring operation [C#]
- refactoring [C#], Encapsulate Field
ms.assetid: bf714a04-ab1e-49ce-99ce-dda1ebb1a17f
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: d587edebcea443e0bfff52004b128c70923470d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="encapsulate-field-refactoring-c"></a>필드 캡슐화 리팩터링(C#)
**필드 캡슐화** 신속 하 게 속성에서 기존 필드를 만들고 다음 새 속성에 대 한 참조로 원활 하 게 코드를 업데이트할 수 있습니다 리팩터링 작업 합니다.  
  
 경우는 [필드](/dotnet/csharp/programming-guide/classes-and-structs/fields) 은 [공용](/dotnet/csharp/language-reference/keywords/public), 다른 개체에 해당 필드에 직접 액세스할 수 있으며 해당 필드를 소유 하는 개체가 사실을 알지 못합니다 수정할 수 있습니다. 사용 하 여 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties) 해당 필드를 캡슐화 하 필드에 직접 액세스를 거부할 수 있습니다.  
  
 새 속성을 만들려면는 **필드 캡슐화** 작업을 캡슐화 할 필드에 대 한 액세스 한정자 변경 [개인](/dotnet/csharp/language-reference/keywords/private), 한 다음 생성 [가져오기](/dotnet/csharp/language-reference/keywords/get)및 [설정](/dotnet/csharp/language-reference/keywords/set) 해당 필드에 대 한 접근자입니다. 필드가 읽기 전용으로 선언되는 경우와 같이 몇몇 경우에는 `get` 접근자만 생성됩니다.  
  
 리팩터링 엔진 코드에 지정 된 영역에 새 속성에 대 한 참조로 업데이트는 **참조 업데이트** 의 섹션은 **필드 캡슐화** 대화 상자.  
  
### <a name="to-create-a-property-from-a-field"></a>필드에서 속성을 만들려면  
  
1.  `EncapsulateFieldExample`이라는 콘솔 응용 프로그램을 만들고 `Program`을 다음 예제 코드로 바꿉니다.  
  
    ```csharp  
    class Square  
    {  
        // Select the word 'width' and then use Encapsulate Field.  
        public int width, height;  
    }  
    class MainClass  
    {  
        public static void Main()  
        {  
            Square mySquare = new Square();  
            mySquare.width = 110;  
            mySquare.height = 150;  
            // Output values for width and height.  
            Console.WriteLine("width = {0}", mySquare.width);  
            Console.WriteLine("height = {0}", mySquare.height);  
        }  
    }  
    ```  
  
2.  에 [코드 편집기](../ide/writing-code-in-the-code-and-text-editor.md)를 캡슐화 할 필드의 이름에는 선언에 커서를 놓습니다. 아래 예제에서 커서를 단어 `width`에 배치합니다.  
  
    ```csharp  
    public int width, height;  
    ```  
  
3.  에 **리팩터링** 메뉴를 클릭 하 여 **필드 캡슐화**합니다.  
  
     **필드 캡슐화** 대화 상자가 나타납니다.  
  
     바로 가기 키 CTRL + R을 표시 하려면 E를 입력할 수도 있습니다는 **필드 캡슐화** 대화 상자.  
  
     커서를을 마우스 오른쪽 단추로 클릭 가리킨 **리팩터링**, 클릭 하 고 **필드 캡슐화** 표시 하는 **필드 캡슐화** 대화 상자.  
  
4.  설정을 지정합니다.  
  
5.  Enter 키를 누르거나는 **확인** 단추입니다.  
  
6.  선택한 경우에 **참조 변경 내용 미리 보기** 옵션을 하면 **참조 변경 내용 미리 보기** 창이 열립니다. 클릭는 **적용** 단추입니다.  
  
     다음 `get` 및 `set` 접근자 코드가 소스 파일에 표시됩니다.  
  
    ```csharp  
    public int Width  
    {  
        get { return width; }  
        set { width = value; }  
    }  
    ```  
  
     `Main` 메서드의 코드도 새 `Width` 속성 이름으로 업데이트됩니다.  
  
    ```csharp  
    Square mySquare = new Square();  
    mySquare.Width = 110;  
    mySquare.height = 150;  
    // Output values for width and height.  
    Console.WriteLine("width = {0}", mySquare.Width);  
    ```  
  
## <a name="remarks"></a>설명  
 **필드 캡슐화** 작업은 필드 선언과 같은 줄에 커서가 위치 하는 경우에 가능 합니다.  
  
 여러 필드를 선언 하는 선언에 대 한 **필드 캡슐화** 쉼표를 사용 하 여 필드를 구분 하 고는 커서와 같은 줄 및 커서와 가장 가까이 있는 필드에 리팩터링을 시작 합니다. 선언에서 필드 이름을 선택하여 캡슐화할 필드를 지정할 수도 있습니다.  
  
 이 리팩터링 작업으로 생성된 코드는 필드 캡슐화 코드 조각 기능을 통해 모델링됩니다. 코드 조각은 수정 가능합니다. 자세한 내용은 [코드 조각](../ide/visual-csharp-code-snippets.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [리팩터링(C#)](refactoring-csharp.md)   
 [Visual C# 코드 조각](../ide/visual-csharp-code-snippets.md)