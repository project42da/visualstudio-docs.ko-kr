---
title: "방법: ClickOnce 응용 프로그램에 데이터 파일 포함 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 데이터"
  - "데이터 액세스, ClickOnce 응용 프로그램"
  - "응용 프로그램 배포[ClickOnce], 데이터 파일"
ms.assetid: 89ee46ef-bc8c-4ab0-a2ac-1220f9da06fc
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: ClickOnce 응용 프로그램에 데이터 파일 포함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

설치되는 각 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서는 대상 컴퓨터의 로컬 컴퓨터에 데이터 디렉터리가 할당되며 이 위치에서 해당 응용 프로그램의 고유한 데이터를 관리할 수 있습니다.  데이터 파일에는 텍스트 파일, XML 파일, Microsoft Access 데이터베이스 파일\(.mdb\) 같은 임의의 파일 형식이 포함될 수 있습니다.  다음 절차에서는 임의의 형식으로 된 데이터 파일을 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 추가하는 방법을 보여 줍니다.  
  
### Mage.exe를 사용하여 데이터 파일을 포함하려면  
  
1.  응용 프로그램의 나머지 파일과 함께 응용 프로그램 디렉터리에 데이터 파일을 추가합니다.  
  
     일반적으로 응용 프로그램 디렉터리의 이름에는 v1.0.0.0 같이 배포의 현재 버전이 사용됩니다.  
  
2.  응용 프로그램 매니페스트를 업데이트하여 데이터 파일을 나열합니다.  
  
     **mage \-u v1.0.0.0\\Application.manifest \-FromDirectory v1.0.0.0**  
  
     이 작업을 수행하면 응용 프로그램 매니페스트에 파일 목록이 다시 작성되고 해시 서명도 자동으로 생성됩니다.  
  
3.  기본 텍스트 편집기나 XML 편집기에서 응용 프로그램 매니페스트를 열고 최근에 추가한 파일에 대한 `file` 요소를 찾습니다.  
  
     `Data.xml`이라는 XML 파일을 추가한 경우 이 요소는 다음 코드 예제와 비슷합니다.  
  
 `<file name="Data.xml" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  이 요소에 `type` 특성을 추가하고 값으로 `data`를 지정합니다.  
  
 `<file name="Data.xml" writeableType="applicationData" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  키 쌍이나 인증서를 사용하여 응용 프로그램 매니페스트에 다시 서명한 다음 배포 매니페스트에 다시 서명합니다.  
  
     응용 프로그램 매니페스트의 해시가 변경되므로 배포 매니페스트에 다시 서명해야 합니다.  
  
     **mage \-s app manifest \-cf cert\_file \-pwd password**  
  
     **mage \-u deployment manifest \-appm app manifest**  
  
     **mage \-s deployment manifest \-cf certfile \-pwd password**  
  
### MageUI.exe를 사용하여 데이터 파일을 포함하려면  
  
1.  응용 프로그램의 나머지 파일과 함께 응용 프로그램 디렉터리에 데이터 파일을 추가합니다.  
  
2.  일반적으로 응용 프로그램 디렉터리의 이름에는 v1.0.0.0 같이 배포의 현재 버전이 사용됩니다.  
  
3.  **파일** 메뉴에서 **열기**를 클릭하여 응용 프로그램 매니페스트를 엽니다.  
  
4.  **파일** 탭을 선택합니다.  
  
5.  탭의 맨 위에 있는 텍스트 상자에 응용 프로그램 파일이 들어 있는 디렉터리를 입력한 다음 **채우기**를 클릭합니다.  
  
     데이터 파일이 모눈에 표시됩니다.  
  
6.  데이터 파일의 **파일 형식** 값을 **데이터**로 설정합니다.  
  
7.  응용 프로그램 매니페스트를 저장한 다음 파일에 다시 서명합니다.  
  
     MageUI.exe에서 파일에 다시 서명하라는 메시지가 표시됩니다.  
  
8.  배포 매니페스트에 다시 서명합니다.  
  
     응용 프로그램 매니페스트의 해시가 변경되므로 배포 매니페스트에 다시 서명해야 합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)