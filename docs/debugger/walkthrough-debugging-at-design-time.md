---
title: 디자인 타임-Visual Studio에 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a2e907cff461852d09e7b5b00482d2bdf42c0340
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-at-design-time-in-visual-studio"></a>Visual Studio에서 디자인 타임에 디버깅

일부 시나리오에서는 디자인에 대 한 코드를 디버깅 하려는 응용 프로그램이 실행 되는 동안에 대신 시간입니다. 사용 하 여 수행할 수 있습니다는 **직접 실행** 창. 데이터 바인딩 코드 등의 다른 코드와 상호 작용 하는 XAML 코드를 디버깅 하려는 경우 사용할 수 있습니다 **디버그** > **프로세스에 연결** 그렇게 하려면.
  
### <a name="debug-at-design-time-using-the-immediate-window"></a>직접 실행 창을 사용 하 여 디자인 타임에 디버깅  

Visual Studio를 사용 하 여 **직접 실행** 응용 프로그램은 실행 되지 않을 때 함수 또는 서브루틴을 실행 하는 창입니다. 함수 또는 서브루틴에 중단점을이 있으면 Visual Studio는 해당 시점에서 실행을 중단 합니다. 그런 다음 디버거 창을 사용하여 프로그램 상태를 조사할 수 있습니다. 이 기능을 디자인 타임에 디버깅 라고 합니다.  

다음 예제에서는 Visual Basic의 경우에 있지만 **직접 실행** C# 및 c + + 응용 프로그램 창 에서도 지원 됩니다.
  
1.  Visual Basic 콘솔 응용 프로그램에 다음 코드를 붙여 넣습니다.  
  
    ```vb  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  읽기, 줄에 중단점을 설정 `s="Add BreakPoint Here"`합니다.  
  
3.  열기는 **직접 실행** 창 (**디버그** > **Windows** > **직접 실행**)에서 다음을 입력 하 고는 창: `?MyFunction<enter>`  
  
4.  중단점이 적중 된 호출 스택의 정확한 지 확인 합니다.  
  
5.  에 **디버그** 메뉴를 클릭 **계속**, 디자인 모드에 있는지 확인 합니다.  
  
6.  다음을 입력 하 고 **직접 실행** 창: `?MyFunction<enter>`  
  
7.  다음을 입력 하 고 **직접 실행** 창: `?MySub<enter>`  
  
8.  중단점에 도달 하 고 정적 변수의 값을 검사 확인 `i` 에 **지역** 창. 값 3 필요 합니다.  
  
9. 호출 스택의 정확한 지 확인 합니다.  
  
10. 에 **디버그** 메뉴를 클릭 **계속**, 디자인 모드에 있는지 확인 합니다.  

## <a name="debug-at-design-time-from-the-xaml-designer"></a>XAML 디자이너에서 디자인 타임에 디버그

코드 숨김 일부 선언적 데이터 바인딩 시나리오의 XAML 디자이너에서 디버깅할 수 있습니다.

1. 프로젝트를 추가 하는 새 XAML 페이지와 같은 *temp.xaml*합니다. 새 XAML 페이지를 비워 둡니다. 

1. 솔루션을 컴파일하십시오.

1. 열기 *temp.xaml*, 디자이너 로드 (*UwpSurface.exe* UWP 앱에서 또는 *XDesProc.exe*) 이후 단계에서 연결할 수 있도록 합니다. 

1. 새 Visual Studio 인스턴스를 엽니다. 새 인스턴스를 열고는 **프로세스에 연결** 대화 상자 (**디버그** > **프로세스에 연결**) 설정는 **연결할** 올바른 코드 형식에 필드를 같은 필드 **관리 코드 (CoreCLR)** 또는 올바른 코드 형식에 따라.NET 버전입니다. 목록에서 올바른 디자이너 프로세스를 선택 하 고 선택 **연결**합니다.

    UWP를 대상으로 하는 프로젝트 작성 16299 또는 디자이너 프로세스는 위, *UwpSurface.exe*합니다. WPF 또는 16299 이전의 UWP의 버전에 대 한 디자이너 과정이 *XDesProc.exe*합니다.

1. 프로세스에 연결 하는 동안에 전환 하 여 프로젝트에 코드를 디버깅 하려면 숨김 열고 중단점을 설정 합니다.

1. 마지막으로 데이터 바인딩을 포함 하는 XAML 코드를 포함 하는 페이지를 엽니다.

    예를 들어 디자인 타임에 TextBlock 바인딩하 다음 XAML을 위한 형식 변환기 코드에서 중단점을 설정할 수 있습니다.

    ```xaml
    <TextBlock Text="{Binding title, ConverterParameter=lower, Converter={StaticResource StringFormatConverter}, Mode=TwoWay}"  />
    ```
   페이지를 로드 하는 경우 중단점이 적중 됩니다.
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [디버거 기본 사항](../debugger/debugger-basics.md)
