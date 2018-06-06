---
title: '방법: 메서드에 매개 변수를 추가 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], adding a method to a parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter
- BDC [SharePoint development in Visual Studio], adding a method to a parameter
- BDC [SharePoint development in Visual Studio], parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], method parameters
- BDC [SharePoint development in Visual Studio], method parameters
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9268fd0deb463a29c8e6d19e98ad63c86b965292
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767090"
---
# <a name="how-to-add-a-parameter-to-a-method"></a>방법: 메서드에 매개 변수를 추가 합니다.
  메서드에서 정보를 반환 하거나 정보를 메서드에 전달 하는 매개 변수를 사용 합니다. 모든 메서드 매개 변수가 하나 이상 있어야 합니다. 만들려는 메서드의 유형을 지원 하도록 매개 변수를 디자인 하는 방법에 대 한 자세한 내용은 참조 하십시오. [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
 메서드에 매개 변수를 추가 하면 Visual Studio 프로젝트에 모델 파일의 XML에 매개 변수 요소를 추가 합니다. 매개 변수 요소는 특성에 대 한 자세한 내용은 참조 [매개 변수](http://go.microsoft.com/fwlink/?LinkId=169284)합니다.  
  
### <a name="to-add-a-parameter-to-a-method"></a>메서드에 매개 변수를 추가하려면  
  
1.  엔터티에 메서드를 추가 합니다.  
  
2.  메뉴 모음에서 **보기** > **다른 창** > **BDC 메서드 세부 정보**합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다. 자세한 내용은 참조 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)합니다.  
  
3.  에 **BDC 메서드 세부 정보** 창에서 노드를 확장 한 다음 확장은 **매개 변수** 노드.  
  
4.  에 **매개 변수를 추가** 목록에서 선택 **매개 변수 만들기**합니다.  
  
     아래에 새 매개 변수 표시는 **매개 변수** 노드.  
  
5.  메뉴 모음에서 **보기** > **속성 창**합니다.  
  
6.  에 **속성** 창의 설정는 **이름** 속성을 쉽게 알아볼 수 있는 모든 이름입니다. 예를 들어 메서드는 고객을 반환 하는 경우 메서드 이름을 수 **GetCustomers**합니다.  
  
7.  에 **BDC 메서드 세부 정보** 창에서 매개 변수의 방향에 대 한 표시 되는 목록을 열고 한 다음 **에**, **InOut**, **아웃**, 또는 **반환**합니다.  
  
     만들고 있는 형식 메서드 선택할 방향에 대 한 자세한 내용은 참조 하십시오. [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
8.  매개 변수의 형식 설명자를 수정 합니다. 자세한 내용은 참조 [하는 방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)합니다.  
  
## <a name="see-also"></a>참고자료
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [방법: 매개 변수의 형식 설명자를 정의 합니다.](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
