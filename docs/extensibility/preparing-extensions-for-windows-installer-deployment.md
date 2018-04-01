---
title: Windows Installer 배포에 대 한 확장을 준비 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vsix msi
ms.assetid: 5ee2d1ba-478a-4cb7-898f-c3b4b2ee834e
caps.latest.revision: 15
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b72fc46d64034ddc22e929fb1a1eff26115cce70
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="preparing-extensions-for-windows-installer-deployment"></a>Windows Installer 배포에 대 한 확장을 준비 하는 중
VSIX 패키지를 배포 하 여 Windows Installer 패키지 (MSI)를 사용할 수 없습니다. 그러나 MSI 배포에 대 한 VSIX 패키지의 내용을 추출할 수 있습니다. 이 문서에는 기본 출력을 가진는 설치 프로젝트에 포함 되도록 하는 VSIX 패키지 프로젝트를 준비 하는 방법을 보여 줍니다.  
  
## <a name="preparing-an-extension-project-for-windows-installer-deployment"></a>Windows Installer 배포를 위한 확장 프로젝트를 준비 하는 중  
 설치 프로젝트에 추가 하기 전에 새 확장 프로젝트에서 이러한 단계를 수행 합니다.  
  
#### <a name="to-prepare-an-extension-project-for-windows-installer-deployment"></a>Windows Installer 배포에 대 한 확장 프로젝트를 준비 하려면  
  
1.  VSPackage, MEF 구성 요소, 편집기 장식 또는 VSIX 매니페스트를 포함 하는 다른 확장성 프로젝트 형식을 만듭니다.  
  
2.  코드 편집기에서 VSIX 매니페스트를 엽니다.  
  
3.  VSIX 매니페스트를의 InstalledByMsi 요소 설정 `true`합니다. VSIX 매니페스트에 대 한 자세한 내용은 참조 하십시오. [VSIX 확장 스키마 2.0 참조](../extensibility/vsix-extension-schema-2-0-reference.md)합니다.  
  
     이 구성 요소를 설치 하는 동안에서 VSIX 설치를 차단 합니다.  
  
4.  프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 클릭 **속성**합니다.  
  
5.  선택 된 **VSIX** 탭 합니다.  
  
6.  레이블이 지정 된 확인란 **다음 위치에 복사 VSIX 콘텐츠** 입력 경로를 여기서 설치 프로젝트 파일을 선택 합니다.  
  
## <a name="extracting-files-from-an-existing-vsix-package"></a>기존 VSIX 패키지에서 파일을 추출합니다.  
 원본 파일이 없는 경우 설치 프로젝트에 기존 VSIX 패키지의 콘텐츠를 추가 하려면 다음이 단계를 수행 합니다.  
  
#### <a name="to-extract-files-from-an-existing-vsix-package"></a>기존 VSIX 패키지에서 파일을 추출  
  
1.  이름 바꾸기는 합니다. VSIX 파일에서 확장을 포함 하 *filename*에.vsix *filename*.zip 합니다.  
  
2.  .Zip 파일의 내용을 디렉터리에 복사 합니다.  
  
3.  디렉터리에서 [Content_types].xml 파일을 삭제 합니다.  
  
4.  이전 절차에서 표시 된 것과 같이 VSIX 매니페스트를 편집 합니다.  
  
5.  설치 프로젝트에 나머지 파일을 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 설치 관리자 배포](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [연습: 사용자 지정 작업 만들기](http://msdn.microsoft.com/en-us/4bd4b63a-2b91-431e-839c-5752443f0eaf)