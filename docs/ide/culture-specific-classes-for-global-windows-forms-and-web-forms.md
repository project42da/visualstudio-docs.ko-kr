---
title: "전역 Windows Forms 및 Web Forms을 위한 문화권 관련 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "전역화[Windows Forms], 클래스"
  - "웹 응용 프로그램[.NET Framework], 전역화"
  - "문화권, 문화권 관련 클래스"
  - "번호, 국가별"
  - "지역화[Windows Forms], 클래스"
  - "전역화[Visual Studio], 문화권 관련 클래스"
  - "Windows Forms, 지역화"
  - "국가별 응용 프로그램[Visual Studio], 데이터 형식"
  - "시간[Visual Studio], 국가별"
  - "날짜[Visual Studio], 국가별"
  - "culture"
  - "국가별 문자"
  - "통화 형식"
  - "ASP.NET, 전역화"
  - "클래스[Visual Studio], 문화권 관련"
  - "지역화[Visual Studio], 문화권 관련 클래스"
ms.assetid: 0d06a0a4-f887-4f7c-bde7-1d543c06f803
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# <a name="culture-specific-classes-for-global-windows-forms-and-web-forms"></a>전역 Windows Forms 및 Web Forms을 위한 문화권 관련 클래스
문화권마다 날짜, 시간, 숫자, 통화 및 기타 정보를 표시하는 규칙이 서로 다릅니다. <xref:System.Globalization> 네임스페이스는 <xref:System.Globalization.DateTimeFormatInfo>, **Calendar**, <xref:System.Globalization.NumberFormatInfo> 등 문화권 관련 값이 표시되는 방식을 수정하는 데 사용할 수 있는 클래스를 포함합니다.  
  
## <a name="using-the-culture-setting"></a>문화권 설정 사용  
 하지만 대부분은 응용 프로그램 또는 **국가별 옵션** 제어판에 저장된 문화권 설정을 사용하여 런타임에 규칙을 자동으로 확인하고 그에 따라 정보의 서식을 지정합니다. 문화권 설정에 대한 자세한 내용은 [방법: Windows Forms 전역화를 위한 문화권 및 UI 문화권 설정](http://msdn.microsoft.com/en-us/694e049f-0b91-474a-9789-d35124f248f0) 또는 [방법: ASP.NET 웹 페이지 세계화를 위한 문화권 및 UI 문화권 설정](http://msdn.microsoft.com/Library/76091f86-f967-4687-a40f-de87bd8cc9a0)을 참조하세요. 문화권 설정에 따라 자동으로 정보의 서식을 지정하는 클래스를 문화권 관련 클래스라고 합니다. 문화권 관련 메서드에는 <xref:System.IFormattable.ToString%2A?displayProperty=fullName>, <xref:System.Console.WriteLine%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> 등이 있습니다. 몇 가지 문화권 관련 함수(Visual Basic 언어)로는 `MonthName` 및 `WeekDayName`이 있습니다.  
  
 예를 들어 다음 코드는 <xref:System.IFormattable.ToString%2A> 메서드를 사용하여 현재 문화권에 대한 통화 서식을 지정하는 방법을 보여 줍니다.  
  
```vb#  
' Put the Imports statements at the beginning of the code module  
Imports System.Threading  
Imports System.Globalization  
' Display a number with the culture-specific currency formatting  
Dim MyInt As Integer = 100  
Console.WriteLine(MyInt.ToString("C", Thread.CurrentThread.CurrentCulture))  
  
```  
  
```c#  
// Put the using statements at the beginning of the code module  
using System.Threading;  
using System.Globalization;  
// Display a number with the culture-specific currency formatting  
int myInt = 100;  
Console.WriteLine(myInt.ToString("C", Thread.CurrentThread.CurrentCulture));  
```  
  
 문화권이 "fr-FR"로 설정된 경우 출력 창에 다음과 같이 표시됩니다.  
  
 `100,00`  
  
 문화권이 "en-US"로 설정된 경우 출력 창에 다음과 같이 표시됩니다.  
  
 `$100.00`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IFormattable.ToString%2A?displayProperty=fullName>   
 <xref:System.Globalization.DateTimeFormatInfo>   
 <xref:System.Globalization.NumberFormatInfo>   
 <xref:System.Globalization.Calendar>   
 <xref:System.Console.WriteLine%2A?displayProperty=fullName>   
 <xref:System.String.Format%2A?displayProperty=fullName>   
 [응용 프로그램 전역화 및 지역화](../ide/globalizing-and-localizing-applications.md)


<!--HONumber=Feb17_HO4-->


