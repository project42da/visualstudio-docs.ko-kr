---
redirect_url: /visualstudio/csharp-ide/refactoring/extract-interface
title: "인터페이스 추출 리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Extract Interface
- Extract Interface refactoring operation [C#]
ms.assetid: 7d0aa225-3b33-4331-9652-5a67cac6f3d0
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4ed81f6f0fbcc2e72fd57d7706b051dcdf7bea75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="extract-interface-refactoring-c"></a>인터페이스 추출 리팩터링(C#)
인터페이스 추출은 기존 클래스, 구조체 또는 인터페이스에서 생성 되는 멤버와 새 인터페이스를 만들 수 있는 간편한 방법을 제공 하는 리팩터링 작업 합니다.  
  
 클래스, 구조체 또는 인터페이스를 멤버의 동일한 하위 집합을 사용 하 여 다 수의 클라이언트 또는 여러 클래스, 구조체 또는 인터페이스 멤버의 하위 집합의 공통점은 인터페이스에서 멤버의 하위 집합을 구현 유용할 수 있습니다. 인터페이스를 사용 하는 방법에 대 한 자세한 내용은 참조 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)합니다.  
  
 인터페이스 추출 새 파일에는 인터페이스를 생성 하 고 새 파일의 시작 부분에 커서가 놓입니다. 새 인터페이스, 새로운 인터페이스의 이름 및 사용 하 여 생성 된 파일의 이름으로 추출할 멤버를 지정할 수는 **인터페이스 추출** 대화 상자.  
  
### <a name="to-use-extract-interface"></a>인터페이스 추출 사용 하려면  
  
1.  라는 콘솔 응용 프로그램 만들기 `ExtractInterface`, 바꿉니다 `Program` 를 다음 코드로  
  
    ```csharp  
    // Invoke Extract Interface on ProtoA.  
    // Note:  the extracted interface will be created in a new file.  
    class ProtoA  
    {  
        public void MethodB(string s) { }  
    }  
    ```  
  
2.  에 커서가 `MethodB`를 클릭 하 고 **인터페이스 추출** 에 **리팩터링** 메뉴.  
  
     **인터페이스 추출** 대화 상자가 나타납니다.  
  
     바로 가기 키 CTRL + R, I 표시를 입력할 수도 있습니다는 **인터페이스 추출** 대화 상자.  
  
     마우스를을 마우스 오른쪽 단추로 클릭 가리킨 **리팩터링**, 클릭 하 고 **인터페이스 추출** 표시 하는 **인터페이스 추출** 대화 상자.  
  
3.  클릭 **모두 선택**합니다.  
  
4.  **확인**을 클릭합니다.  
  
     새 파일, IProtoA.cs, 및 다음 코드를 볼 수 있습니다.  
  
    ```csharp  
    using System;  
    namespace TopThreeRefactorings  
    {  
        interface IProtoA  
        {  
            void MethodB(string s);  
        }  
    }  
    ```  
  
## <a name="remarks"></a>설명  
 이 기능은 커서가 클래스, 구조체 또는 인터페이스를 추출 하려는 멤버를 포함 하는 경우에 액세스할 수 있습니다. 커서가이 위치에 있을 때 인터페이스 추출 리팩터링 작업을 호출 합니다.  
  
 클래스 또는 구조체에 추출 인터페이스를 호출할 때 기본 및 인터페이스 목록 새 인터페이스 이름을 포함 하도록 수정 됩니다. 인터페이스에서 추출 인터페이스를 호출 하면 기본 및 인터페이스 목록 수정 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [리팩터링(C#)](refactoring-csharp.md)