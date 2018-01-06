---
title: "방법: 코드 지역화 | Microsoft Docs"
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
- localizing code [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
ms.assetid: 0e852052-5ad4-4517-81cf-8865ec304441
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4e920074f6f771c2b8e5a78b128bf3b1f096d77e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-localize-code"></a>방법: 코드 지역화
  지역화 되지 않은 코드 하드 코드 된 문자열 값을 사용합니다. 에 대 한 호출으로 대체 코드 문자열을 지역화 하려면 <xref:System.Web.HttpContext.GetGlobalResourceObject%2A>, 지역화 된 리소스를 참조 하는 방법인 합니다.  
  
## <a name="localizing-code"></a>코드 지역화  
  
#### <a name="to-localize-code"></a>코드 필드를 지역화  
  
1.  **솔루션 탐색기**, 프로젝트 항목에 대 한 바로 가기 메뉴를 열고 선택한 후 **추가**, **모듈**합니다.  
  
     선택 된 **리소스 파일** 템플릿.  
  
    > [!NOTE]  
    >  배포 유형의 속성을 사용할 수 있도록 SharePoint 프로젝트 항목에 리소스 파일을 추가 해야 합니다. 이 속성은이 절차의 뒷부분에 나오는 필요 합니다.  
  
2.  기본 언어 리소스 파일 MyAppResources.resx 같은.resx 확장명을 추가 하거나 원하는 이름을 지정 합니다.  
  
3.  1단계와 2단계를 반복하여 지역화된 언어마다 하나씩 별도의 리소스 파일을 SharePoint 프로젝트 항목에 추가합니다.  
  
     각 지역화 된 리소스 파일에 동일한 기본 이름을 사용 하지만 추가 문화권 id입니다. 예를 들어 독일어 지역화 된 리소스 MyAppResources.de 같은 이름을 지정 합니다.  
  
4.  각 리소스 파일을 열고 지역화 된 문자열을 추가 합니다. 각 파일에서 동일한 문자열 ID를 사용합니다.  
  
5.  값을 변경는 **배포 유형을** 각 리소스 파일의 속성 **AppGlobalResource** 를 각 파일이 서버의 App_GlobalResources 폴더에 배포 되도록 합니다.  
  
6.  값을 지정 하지는 **빌드 작업** 으로 각 파일의 속성 **포함 리소스**합니다.  
  
     포함 리소스는 프로젝트의 DLL로 컴파일됩니다.  
  
7.  리소스 위성 Dll을 만들려면 프로젝트를 빌드하십시오.  
  
8.  에 **패키지 디자이너**, 선택는 **고급** 탭을 클릭 한 다음 위성 어셈블리를 추가 합니다.  
  
9. 에 **위치** 상자, DE-DE 등 위치 경로에 문화권 ID 폴더 앞에 추가\\*프로젝트 항목 이름*. resources.dll 합니다.  
  
10. 솔루션에 System.Web 어셈블리를 이미 참조 하지 않는 경우,에 대 한 참조를 추가 하 고 코드에 지시문을 추가 <xref:System.Web>합니다.  
  
11. 사용자에게 표시되는 코드에서 UI 텍스트, 오류 및 메시지 텍스트와 같은 하드 코딩된 모든 문자열을 찾습니다. 다음 구문을 사용하여 <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> 메서드를 호출하여 이러한 문자열을 바꿉니다.  
  
    ```  
    HttpContext.GetGlobalResourceObject("Resource File Name", "String ID")  
    ```  
  
12. F5 키를 선택하여 응용 프로그램을 빌드하고 실행합니다.  
  
13. Sharepoint의 기본에서 표시 언어를 변경 합니다.  
  
     지역화 된 문자열 응용 프로그램에 나타납니다. 지역화 된 리소스를 표시 하려면 SharePoint 서버에서 리소스 파일의 문화권과 일치 하는 언어 팩 설치 되어 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)   
 [방법: 기능 지역화](../sharepoint/how-to-localize-a-feature.md)   
 [방법: ASPX 태그 지역화](../sharepoint/how-to-localize-aspx-markup.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)  
  
  