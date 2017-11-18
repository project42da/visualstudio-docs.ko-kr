---
title: "형식 지정자 (C#) 디버거에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- expressions [C#], formatting values
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- specifiers, watch variable format
- QuickWatch dialog box, format specifiers in C#
- specifiers
- watch variable symbols
- Watch window, format specifiers in C#
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 345c8589-5f36-4d34-a58c-e56271687dd6
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: edb41f8fea8447f8616b4c20f442ffd4fa8b48c8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="format-specifiers-in-c-in-the-visual-studio-debugger"></a>Visual Studio 디버거에서의 C#의 형식 지정자
형식 지정자를 사용하여 **조사식** 창에 값이 표시되는 형식을 변경할 수 있습니다. 또한 **직접 실행** 창, **명령** 창 및 소스 창에서도 형식 지정자를 사용할 수 있습니다. 이러한 창에서 식을 일시 중지하면 결과가 DataTip에 나타납니다. DataTip 보기에는 형식 지정자에 맞는 DataTip이 표시됩니다.  
  
 형식 지정자를 사용하려면 식을 입력한 다음 쉼표를 입력합니다. 쉼표 뒤에 적절한 지정자를 추가합니다.  
  
## <a name="using-format-specifiers"></a>형식 지정자 사용  
 다음과 같은 코드를 가정해 봅니다.  
  
```CSharp  
{  
        int my_var1 = 0x0065;  
        int my_var2 = 0x0066;  
        int my_var3 = 0x0067;  
}  
```  
  
 추가 `my_var1` 조사식 창에 변수 (디버깅 하는 동안 **디버그 > Windows > 조사식 > 조사식 1**)는 표시를 16 진수로 설정 (에 **조사식** 창 변수를 마우스 오른쪽 단추로 클릭 하 고 선택 **16 진수 표시**). 이제는 **조사식** 창에서 변수의 값이 0x0065로 표시됩니다. 이 값을 16진수 정수 대신 10진수 정수로 표시하려면 이름 열에서 변수 이름 뒤에 10진수 형식 지정자 **, d**를 추가합니다. 이제 값 열에 10진수 값 101이 표시됩니다.  
  
 ![WatchFormatCSharp](../debugger/media/watchformatcsharp.png "WatchFormatCSharp")  
  
## <a name="format-specifiers"></a>형식 지정자  
 다음 표에서는 디버거에서 인식할 수 있는 C# 형식 지정자를 보여 줍니다.  
  
|지정자|형식|원래 조사식 값|표시|  
|---------------|------------|--------------------------|--------------|  
|ac|식을 계산합니다. 암시적 속성 확인과 암시적 함수 호출이 해제된 경우에 유용할 수 있습니다.|"암시적 함수 실행은 해제 되어 사용자가" 메시지|\<값 >|  
|일|10진수 정수|0x0065|101|  
|dynamic|동적 뷰를 사용하여 지정된 개체를 표시합니다.|동적 뷰를 포함하여 개체의 모든 멤버를 표시합니다.|동적 뷰만 표시합니다.|  
|h|16진수 정수|61541|0x0000F065|  
|nq|따옴표 없는 문자열|"My String"|My String|  
|hidden|모든 public 멤버 및 public이 아닌 멤버를 표시합니다.|공용 멤버를 표시합니다.|모든 멤버를 표시합니다.|  
|raw|항목을 원시 항목 노드에 나타나는 대로 표시합니다. 프록시 개체에만 사용할 수 있습니다.|사전\<T >|raw 뷰\<T >|  
|results|IEnumerable 또는 IEnumerable을 구현 하는 형식의 변수와 함께 사용할\<T >, 일반적으로 쿼리 식의 결과입니다. 쿼리 결과가 포함된 멤버만 표시합니다.|모든 멤버를 표시합니다.|쿼리 조건에 맞는 멤버를 표시합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [조사식 및 간략 한 조사식 창](../debugger/watch-and-quickwatch-windows.md)   
 [자동 및 지역 창](../debugger/autos-and-locals-windows.md)
