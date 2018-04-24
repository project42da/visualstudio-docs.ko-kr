---
title: '방법: ClickOnce 응용 프로그램에 대 한 시작 메뉴 이름 지정 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a089fa67c975496c56d29d2d55c2f055888c96d9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램의 시작 메뉴 이름 지정
경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 온라인 및 오프 라인 사용 하 여 응용 프로그램 설치에 항목이 추가 되는 **시작** 메뉴 및 **프로그램 추가 / 제거** 목록입니다. 기본적으로는 표시 이름은 응용 프로그램 어셈블리의 이름과 동일 같지만 표시 이름을 설정 하 여 변경할 수 있습니다 **제품 이름** 에 **게시 옵션** 대화 상자.  
  
 **제품 이름** 표시 되는 publish.htm 페이지는;에 설치 된 오프 라인 응용 프로그램에 있는 항목의 이름이 됩니다는 **시작** 메뉴에 표시 되는 이름은 수도 있습니다 **추가 또는 제거 프로그램**합니다.  
  
 **게시자 이름** 위의 publish.htm 페이지에 표시 될 **제품 이름**, 설치 된 오프 라인 응용 프로그램에 대 한도 것에서 응용 프로그램의 아이콘을 포함 하는 폴더의 이름을 **시작**  메뉴.  
  
 설정할 수 있습니다는 **제품 이름** 및 **게시자 이름** 속성에는 **게시 옵션** 에서 사용할 수 있는 대화 상자는 **게시** 페이지 **프로젝트 디자이너**합니다.  
  
### <a name="to-specify-a-start-menu-name"></a>시작 메뉴 이름 지정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  클릭는 **옵션** 버튼을 클릭은 **게시 옵션** 대화 상자.  
  
4.  클릭 **설명**합니다.  
  
5.  에 **게시 옵션** 대화 상자에 표시할 이름을 입력 합니다 **제품 이름**합니다.  
  
6.  게시자 이름을 입력할 수는 필요에 따라 **게시자 이름**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)