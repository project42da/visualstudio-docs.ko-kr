---
title: "Office의 스레딩 지원 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- multiple threads [Office development in Visual Studio]
- threading [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], threading support
- object models [Office development in Visual Studio], threading support
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3383e3767c97efad9177f0e361524137ea5d66a8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="threading-support-in-office"></a>Office의 스레딩 지원
  이 항목에서는 Microsoft Office 개체 모델에서 스레딩 지 원하는 하는 방법에 대 한 정보를 제공 합니다. Office 개체 모델은 스레드로부터 안전 하지 하지만 Office 솔루션에서 여러 스레드를 작성 하려면 가능 합니다. Office 응용 프로그램은 서버 구성 요소 개체 모델 (COM). COM 클라이언트가 임의 스레드에서 COM 서버를 호출할 수 있습니다. 스레드로부터 안전 하지 않은 COM 서버에 대 한 하나의 논리 스레드가 언제 든 지 서버에서 실행 되도록 동시 호출을 serialize 하는 메커니즘을 제공 합니다. 이 메커니즘은 단일 스레드 아파트 (STA) 모델 이라고 합니다. 호출이 serialize 되므로 서버 사용 되 고 있거나 백그라운드 스레드에 대 한 다른 호출을 처리 하는 동안 기간에 대 한 호출자가 차단 될 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="knowledge-required-when-using-multiple-threads"></a>여러 스레드를 사용 하는 경우 필수 기술  
 여러 스레드를 사용 하려면 다음과 같은 측면을 기본적으로 알고 있어야 다중 스레딩:  
  
-   Windows Api  
  
-   COM 다중 스레드 개념  
  
-   동시성  
  
-   동기화  
  
-   마샬링  
  
 일반 정보에 대 한 다중 스레딩에 대 한 참조 [관리 되는 스레딩](/dotnet/standard/threading/)합니다.  
  
 Office 주 STA에서 실행 이것의 의미를 이해 하면 Office와 함께 여러 스레드를 사용 하는 방법을 이해할 수 있습니다.  
  
## <a name="basic-multithreading-scenario"></a>다중 스레딩 기본 시나리오  
 Office 솔루션에서 코드는 항상 주 UI 스레드에서 실행 됩니다. 백그라운드 스레드에서 별도 작업을 실행 하 여 응용 프로그램 성능을 개선할 할 수 있습니다. 목표는 두 작업을 완료 겉보기 한 번에 하나 이상의 태스크 뒤에 다른 원활 하 게 실행 (다중 스레드 사용 하는 주요 이유)을 유발 하는 대신입니다. 예를 들어 주 Excel UI 스레드에서 이벤트 코드를 할 수 있습니다 및 백그라운드 스레드는 서버에서 데이터를 수집 하 고 서버에서 데이터와 Excel UI 셀을 업데이트 하는 작업을 실행할 수 있습니다.  
  
## <a name="background-threads-that-call-into-the-office-object-model"></a>Office 개체 모델을 호출 하는 백그라운드 스레드  
 백그라운드 스레드 Office 응용 프로그램에 대 한 호출을 호출 자동으로 STA 경계를 넘어 마샬링됩니다. 그러나 보장이 없습니다 Office 응용 프로그램 시간에 백그라운드 스레드에서 호출을 처리할 수 있습니다. 일부의 가능성이 있습니다.  
  
1.  Office 응용 프로그램에는 입력 수에 대 한 호출에 대 한 메시지 펌프 해야 합니다. 수행 중인 경우이 차이 계산 하지 않고 처리 작업이 너무 많은 시간이 걸릴 수 있습니다.  
  
2.  다른 논리 스레드 아파트에 이미 있으면 새 스레드를 입력할 수 없습니다. 논리 스레드 Office 응용 프로그램을 입력 하 고 다음 호출자의 아파트에 다시 재진입 호출을 수행 하는 경우에 종종 발생 합니다. 응용 프로그램은 해당 호출이 반환 될 때까지 기다리는 차단 됩니다.  
  
3.  들어오는 호출을 즉시 처리할 수 없는 되도록 Excel는 상태일에서 수 있습니다. 예를 들어 Office 응용 프로그램에는 모달 대화 상자가 표시 될 수 있습니다.  
  
 COM은 한 비즈니스 가능성이 2와 3에 대 한 다음을 제공 합니다.는 [IMessageFilter](http://msdn.microsoft.com/en-us/e12d48c0-5033-47a8-bdcd-e94c49857248) 인터페이스입니다. 모든 호출을 통해 입력 서버를 구현 하는 경우는 [HandleIncomingCall](http://msdn.microsoft.com/en-us/7e31b518-ef4f-4bdd-b5c7-e1b16383a5be) 메서드. 2 가능성에 대 한 호출은 자동으로 거부 됩니다. 세 번째 서버는 상황에 따라 호출을 거부할 수 있습니다. 호출이 거부 될 경우 수행할 작업을 호출자에 게 결정 해야 합니다. 일반적으로 호출자에 게 구현 [IMessageFilter](http://msdn.microsoft.com/en-us/e12d48c0-5033-47a8-bdcd-e94c49857248),이 경우가 거부 알림을 받을 것는 [RetryRejectedCall](http://msdn.microsoft.com/en-us/3f800819-2a21-4e46-ad15-f9594fac1a3d) 메서드.  
  
 그러나 경우 Visual Studio에서 Office 개발 도구를 사용 하 여 만든 솔루션, COM interop 변환에 대 한 모든 거부 된 호출을 <xref:System.Runtime.InteropServices.COMException> ("메시지 필터가 표시 응용 프로그램은 사용 중"). 개체 모델을 호출할 때마다 수행한 백그라운드 스레드에서이 예외를 처리 하도록 준비 해야 합니다. 일반적으로 특정 시간 동안 다시 시도 하 고 다음 대화 상자를 표시 합니다. 그러나 백그라운드 스레드를 STA로 만들 수도 하 고이 경우를 처리 하는 스레드에 대 한 메시지 필터를 등록할 수 있습니다.  
  
## <a name="starting-the-thread-correctly"></a>올바른 스레드 시작  
 새 STA 스레드를 만들 때에 스레드를 시작 하기 전에 아파트 상태를 STA로 설정 합니다. 다음 코드 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[Trin_VstcoreCreatingExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/ThisWorkbook.cs#5)]
 [!code-vb[Trin_VstcoreCreatingExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/ThisWorkbook.vb#5)]  
  
 자세한 내용은 참조 [관리 되는 스레딩 유용한](/dotnet/standard/threading/managed-threading-best-practices)합니다.  
  
## <a name="modeless-forms"></a>모덜리스 폼  
 모덜리스 폼 폼이 표시 하는 동안 일부 종류의 응용 프로그램과 상호 작용을 허용 합니다. 폼을와 상호 작용할 및 양식을 닫지 않고 응용 프로그램 상호 작용 합니다. Office 개체 모델에는 관리 되는 모덜리스 폼; 지원 그러나 백그라운드 스레드에서 사용 하지 않아야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 스레드](/dotnet/standard/threading/)  
 [스레딩 (C#)](/dotnet/csharp/programming-guide/concepts/threading/index) [스레딩 (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/threading/index)   
 [스레드 및 스레딩 사용](/dotnet/standard/threading/using-threads-and-threading)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  