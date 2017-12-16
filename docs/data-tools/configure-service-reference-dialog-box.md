---
title: "서비스 참조 대화 상자 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 0826d241cc1f3741a35e635bc27dff1d69ad86af
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="configure-service-reference-dialog-box"></a>서비스 참조 구성 대화 상자
**서비스 참조 구성** 대화 상자를 사용 하면 동작을 구성할 수 있습니다 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 서비스입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 액세스는 **서비스 참조 구성** 에서 참조 하는 대화 상자에서 마우스 오른쪽 단추로 서비스 **솔루션 탐색기** 선택 **서비스 참조 구성**합니다. 클릭 하 여 대화 상자에 액세스할 수도 있습니다는 **고급** 단추는 **서비스 참조 추가 대화 상자**합니다.  
  
## <a name="task-list"></a>작업 목록  
  
-   WCF 서비스가 호스팅되는 주소를 변경 하려면 입력에서 새 주소는 **주소** 필드입니다.  
  
-   클래스는 WCF 클라이언트에 대 한 액세스 수준을 변경 하려면 선택의 액세스 수준 키워드는 **액세스 수준을 생성 된 클래스에 대 한** 목록입니다.  
  
-   WCF 서비스의 메서드를 비동기적으로 호출 하려면 다음을 선택 된 **비동기 작업 생성** 확인란 합니다.  
  
-   WCF 클라이언트에서 메시지 계약 형식을 생성 하려면 선택은 **항상 메시지 계약 생성** 확인란 합니다.  
  
-   형식을 선택 목록 또는 사전 컬렉션 형식을 WCF 클라이언트를 지정 하려면는 **컬렉션 형식** 및 **사전 컬렉션 형식** 나열 합니다.  
  
-   형식 공유를 해제 하려면 선택을 취소는 **참조 된 어셈블리의 형식 재사용** 확인란 합니다. 참조 된 어셈블리의 하위 집합에 대해 형식 공유를 사용 하려면 선택은 **참조 된 어셈블리의 형식 재사용** 확인란을 선택 **지정된 된 어셈블리의 형식 재사용**, 원하는 선택 참조 된 **참조 된 어셈블리 목록**합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **주소**  
 서비스 참조가 서비스를 검색하는 웹 주소를 업데이트하는 데 사용됩니다. 예를 들어 개발 도중 서비스를 개발 서버에서 호스팅하다가 나중에 프로덕션 서버로 이동하여 주소를 변경해야 하는 경우가 이에 해당할 수 있습니다.  
  
> [!NOTE]
>  Address 요소 사용할 수 없는 경우는 **서비스 참조 구성** 에서 대화 상자가 표시 됩니다는 **서비스 참조 추가 대화 상자**합니다.  
  
 **생성 된 클래스에 대 한 액세스 수준**  
 WCF 클라이언트 클래스에 대한 코드 액세스 수준을 결정합니다.  
  
> [!NOTE]
>  웹 사이트 프로젝트의 경우 이 옵션은 항상 `Public`으로 설정되며 변경할 수 없습니다. 자세한 내용은 참조 [서비스 참조 문제 해결](../data-tools/troubleshooting-service-references.md)합니다.  
  
 **비동기 작업 생성**  
 WCF 서비스 메서드를 동기적으로(기본값) 호출할지 아니면 비동기적으로 호출할지를 결정합니다.  
  
 **작업 기반 작업 생성**  
 비동기 코드를 작성하는 경우 이 옵션을 사용하면 .Net 4에 도입된 TPL(작업 병렬 라이브러리)을 활용할 수 있습니다. 참조 [작업 병렬 라이브러리 (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl)합니다.  
  
 **항상 메시지 계약 생성**  
 WCF 클라이언트에 대해 메시지 계약 형식을 생성할지 여부를 결정합니다. 메시지 계약에 대 한 자세한 내용은 참조 [메시지 계약을 사용 하 여](/dotnet/framework/wcf/feature-details/using-message-contracts)합니다.  
  
 **컬렉션 형식**  
 WCF 클라이언트에 대한 목록 컬렉션 형식을 지정합니다. 기본 형식은 <xref:System.Array>입니다.  
  
 **사전 컬렉션 형식**  
 WCF 클라이언트에 대한 사전 컬렉션 형식을 지정합니다. 기본 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.  
  
 **참조 된 어셈블리의 형식 재사용**  
 서비스가 추가 또는 업데이트되면 WCF 클라이언트에서 새 형식을 생성하는 대신 참조된 어셈블리에 이미 있는 형식을 다시 사용하도록 할지 여부를 결정합니다. 기본적으로 이 옵션은 선택되어 있습니다.  
  
 **참조 된 모든 어셈블리의 형식 재사용**  
 을 선택 하 고 모든 형식에는 **참조 된 어셈블리 목록** 가능 하면 다시 사용 됩니다. 기본적으로 이 옵션이 선택됩니다.  
  
 **지정된 된 어셈블리의 형식 재사용**  
 선택한 형식만 선택 하면는 **참조 된 어셈블리 목록** 다시 사용 됩니다.  
  
 **참조 된 어셈블리 목록**  
 프로젝트 또는 웹 사이트의 참조된 어셈블리 목록을 포함합니다. 때 **지정된 된 어셈블리의 형식 재사용** 을 선택 하면 개별 어셈블리를 선택 하거나 선택을 취소 해야 합니다.  
  
 **웹 참조 추가**  
 표시는 [웹 참조 추가 대화 상자](https://msdn.microsoft.com/en-us/library/8dcbc50t(v=vs.100).aspx)합니다.  
  
> [!NOTE]
>  이 옵션은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 버전을 대상으로 하는 프로젝트에만 사용해야 합니다.  
  
> [!NOTE]
>  **웹 참조 추가** 단추는 경우에만 사용할 수는 **서비스 참조 구성** 에서 대화 상자가 표시 됩니다는 **서비스 참조 추가 대화 상자**합니다.  
  
## <a name="see-also"></a>참고 항목  

 [방법: 웹 서비스에 대 한 참조를 추가 합니다.](how-to-add-update-or-remove-a-wcf-data-service-reference.md)   
 [Windows Communication Foundation 서비스 및 WCF Data Services](../data-tools/configure-service-reference-dialog-box.md)