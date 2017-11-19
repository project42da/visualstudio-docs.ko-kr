---
title: "방법: ClickOnce 응용 프로그램에 데이터 파일 포함 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, data
- deploying applications [ClickOnce], data files
- data access, ClickOnce applications
ms.assetid: 89ee46ef-bc8c-4ab0-a2ac-1220f9da06fc
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: b03083ce6e9fe7fcebdad0b82373bee41221bbb5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-include-a-data-file-in-a-clickonce-application"></a>How to: Include a Data File in a ClickOnce Application
각 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치한 응용 프로그램 데이터 디렉터리 응용 프로그램 자체 데이터를 관리할 수 있는 대상 컴퓨터의 로컬 디스크에 할당 됩니다. 데이터 파일의 파일 형식 포함할 수 있습니다: 텍스트 파일, XML 파일 또는 Microsoft Access 데이터베이스 (.mdb) 파일도 합니다. 다음 절차에 모든 형식의 데이터 파일을 추가 하는 방법을 보여 줍니다. 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
### <a name="to-include-a-data-file-by-using-mageexe"></a>Mage.exe를 사용 하 여 데이터 파일을 포함 하려면  
  
1.  응용 프로그램의 파일의 나머지와 응용 프로그램 디렉터리에 데이터 파일을 추가 합니다.  
  
     일반적으로 응용 프로그램 디렉터리에 배포의 현재 버전으로 레이블이 지정 된 디렉터리 됩니다-예를 들어 v1.0.0.0 합니다.  
  
2.  데이터 파일을 나열 하 여 응용 프로그램 매니페스트를 업데이트 합니다.  
  
     **mage-u v1.0.0.0\Application.manifest-FromDirectory v1.0.0.0**  
  
     이 작업을 수행 하면 응용 프로그램 매니페스트에 파일 목록이 다시 만듭니다를 자동으로 해시 서명을 생성 합니다.  
  
3.  기본 텍스트 편집기 또는 XML 편집기에서 응용 프로그램 매니페스트를 열고를 찾습니다는 `file` 최근에 추가한 파일에 대 한 요소입니다.  
  
     이라는 XML 파일을 추가한 경우 `Data.xml`, 파일은 다음 코드 예제와 같이 표시 됩니다.  
  
 `<file name="Data.xml" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  특성 추가 `type` 를이 요소에 값이 제공 `data`합니다.  
  
 `<file name="Data.xml" writeableType="applicationData" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  키 쌍 또는 인증서를 사용 하 여 응용 프로그램 매니페스트에 다시 서명 하 고 배포 매니페스트에 다시 서명 합니다.  
  
     응용 프로그램 매니페스트의 해당 해시가 변경 되었기 때문에 배포 매니페스트를 다시 서명 해야 합니다.  
  
     **mage-s 응용 프로그램 매니페스트-cf cert_file-pwd 암호**  
  
     **mage-u 배포 매니페스트 appm 응용 프로그램 매니페스트**  
  
     **mage-s 배포 매니페스트-cf certfile-pwd 암호**  
  
2.  
  
### <a name="to-include-a-data-file-by-using-mageuiexe"></a>MageUI.exe를 사용 하 여 데이터 파일을 포함 하려면  
  
1.  응용 프로그램의 파일의 나머지와 응용 프로그램 디렉터리에 데이터 파일을 추가 합니다.  
  
2.  일반적으로 응용 프로그램 디렉터리에 배포의 현재 버전으로 레이블이 지정 된 디렉터리 됩니다-예를 들어 v1.0.0.0 합니다.  
  
3.  에 **파일** 메뉴를 클릭 하 여 **열** 응용 프로그램 매니페스트를 엽니다.  
  
4.  선택 된 **파일** 탭 합니다.  
  
5.  탭의 위쪽에 텍스트 상자에 응용 프로그램의 파일을 포함 하는 디렉터리를 입력 한 다음 클릭 **채우기**합니다.  
  
     데이터 파일은 표에 표시 됩니다.  
  
6.  설정의 **파일 형식을** 데이터 파일의 값 **데이터**합니다.  
  
7.  응용 프로그램 매니페스트를 저장 하 고 파일에 다시 서명 합니다.  
  
     MageUI.exe는 파일에 다시 서명 하는 라는 메시지가 나타납니다.  
  
8.  배포 매니페스트에 다시 서명  
  
     응용 프로그램 매니페스트의 해당 해시가 변경 되었기 때문에 배포 매니페스트를 다시 서명 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)