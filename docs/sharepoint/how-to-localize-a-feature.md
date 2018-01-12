---
title: "방법: 기능 지역화 | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- features [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1ddb5e705fd581ce2717539ac6daf3e9a2081f6d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-localize-a-feature"></a>방법: 기능 지역화
  기본적으로 기능 제목 및 설명 하드 코드 된 문자열 값을 사용 합니다. 기능 제목 및 설명 필드를 지역화, 지역화 된 리소스를 참조 하는 식으로 문자열을 대체 합니다.  
  
## <a name="localizing-a-feature"></a>기능 지역화  
  
#### <a name="to-localize-a-feature"></a>기능을 지역화 하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **Feature1** 노드를 선택한 후 **기능 리소스 추가**합니다.  
  
2.  에 **리소스 추가** 대화 상자에서 선택 **고정 언어** 기본 언어 기능 리소스 파일에 대 한 문화권에 따라 목록에서 합니다.  
  
3.  지역화된 언어마다 이전 단계를 반복하여 지역화된 기능 리소스 파일에 대해 선택한 언어를 선택합니다.  
  
     기본 언어와 지원할 지역화된 언어마다 하나씩 별도의 기능 리소스 파일이 만들어집니다.  
  
4.  리소스 편집기에서 각 리소스 파일을 연 다음 문자열 ID와 그 값을 모두 입력합니다.  
  
     예를 들어 기본 기능 리소스 파일의 문자열 ID를 입력 **제목** 값 **내 기능 제목의**, 두 번째 문자열의 ID 및 **설명** 값 **내 기능 설명**합니다. 지역화된 각 리소스 파일에 대해 기본 기능 리소스에서 사용된 동일한 문자열 ID를 사용하지만 값의 지역화된 문자열을 입력합니다.  
  
5.  모든 리소스 값을 입력 한 후 (예를 들어, Feature1.feature) 기능에 대 한 바로 가기 메뉴를 열고 선택한 후 **뷰 디자이너** 하 여 기능 디자이너에서 기능을 엽니다.  
  
6.  지역화 하는 **제목** 및 **설명** 필드는 기능에는 다음 형식을 사용 하 여 해당 상자에 값을 입력 합니다.  
  
     `$Resources:`*문자열 ID*  
  
     예를 들어 $Resources 입력:**제목** 에 **기능 제목은** 상자 및 $Resources:**설명** 에 **기능 설명** 상자 .  
  
     문자열 ID는 리소스 파일에서 사용되는 것과 일치해야 합니다.  
  
7.  F5 키를 선택하여 응용 프로그램을 빌드하고 실행합니다.  
  
8.  Sharepoint에서 열고는 **사이트 작업** 메뉴 선택 **사이트 설정**를 선택한 후는 **사이트 작업** 섹션 선택는 **사이트기능관리** 링크 합니다.  
  
9. Sharepoint의 기본에서 표시 언어를 변경 합니다.  
  
     지역화 된 기능 제목 및 설명에는 응용 프로그램에 나타납니다. 지역화 된 리소스를 표시 하려면 SharePoint 서버에서 리소스 파일의 문화권과 일치 하는 언어 팩 설치 되어 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)   
 [방법: ASPX 태그 지역화](../sharepoint/how-to-localize-aspx-markup.md)   
 [방법: 코드 지역화](../sharepoint/how-to-localize-code.md)  
  
  