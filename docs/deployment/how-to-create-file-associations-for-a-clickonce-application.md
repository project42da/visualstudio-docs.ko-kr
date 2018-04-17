---
title: '방법: ClickOnce 응용 프로그램에 대 한 파일 연결 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 75215164de3aedfe1ea0168275280304dfd5def9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램에 대한 파일 연결 만들기
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 시작 될 때 사용자가 해당 형식의 파일을 열 수 있도록 응용 프로그램은 하나 이상의 파일 이름 확장명에 연결할 수 있습니다. 에 파일 이름 확장명 지원을 추가 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 간단 합니다.  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>ClickOnce 응용 프로그램에 대 한 파일 연결을 만들려면  
  
1.  만들기는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 정상적으로 사용 하 여 기존 또는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
2.  텍스트 또는 XML 편집기, 메모장과 같은 응용 프로그램 매니페스트를 엽니다.  
  
3.  `assembly` 요소를 찾습니다. 자세한 내용은 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)를 참조하세요.  
  
4.  자식으로는 `assembly` 요소를 추가 `fileAssociation` 요소입니다. `fileAssociation` 요소에는 네 개의 특성이 있습니다.  
  
    -   `extension`응용 프로그램에 연결 하려는: 파일 이름 확장명입니다.  
  
    -   `description`: Windows 셸에 표시 되는 파일 형식의 설명입니다.  
  
    -   `progid`: 고유 하 게 식별 하는 레지스트리에서 항목을 표시 하는 파일 유형는 문자열입니다.  
  
    -   `defaultIcon`:이 파일 형식에 대해 사용할 아이콘. 응용 프로그램 매니페스트에서 파일 리소스로 아이콘 추가 되어야 합니다. 자세한 내용은 [방법: ClickOnce 응용 프로그램에 데이터 파일 포함](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)을 참조하세요.  
  
     에 대 한 예제는 `file` 및 `fileAssociation` 요소 참조 [ \<fileAssociation > 요소](../deployment/fileassociation-element-clickonce-application.md)합니다.  
  
5.  둘 이상의 파일 형식을 응용 프로그램에 연결 하려는 경우 더 추가 `fileAssociation` 요소입니다. `progid` 특성 마다 달라 야 합니다.  
  
6.  응용 프로그램 매니페스트 마쳤으면 매니페스트에 다시 서명 합니다. Mage.exe를 사용 하 여 명령줄에서 수행할 수 있습니다.  
  
     `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
     자세한 내용은 참조 [Mage.exe (매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)  
  
## <a name="see-also"></a>참고 항목  
 [\<fileAssociation > 요소](../deployment/fileassociation-element-clickonce-application.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)