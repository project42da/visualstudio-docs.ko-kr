---
title: "파일 이름 확장명에 대 한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4aba03fd68fc5e0e68dbf13887de0c25094fa951
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="about-file-name-extensions"></a>파일 이름 확장명에 대 한
버전과 연결 하는 VSPackage의 파일 확장명을 등록 하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 이 중요 한 경우 두 개 이상의 한 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 컴퓨터에 설치 합니다.  
  
 Vspackage에 대 한 파일 확장명은 연결 된 ProgID (프로그래밍 식별자)를 가리키는 기본값을 사용 하 여 HKEY_CLASSES_ROOT 키 아래에서 등록 됩니다.  
  
 다음은.vcproj 파일 확장명에 대 한 등록 정보의 예입니다.  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 연결 된 파일 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전이 지정 된 ProgID와 같은 있어야 `VisualStudio.vcproj.8.0`, 제품 버전 간에 파일 확장명 연결을 유지 하기 위해 제품의 함께-설치를 허용 하도록 합니다. 버전 별로 ProgID 또한 열려 편집 등과 같은 등의 다른 응용 프로그램 또는 버전의에서 덮어쓰이지 우려 없이 표준 동사를 사용할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
 경우에 따라 파일 확장명과 연결 된 ProgID 변경할 수 없습니다. 예를 들어.htm 파일 확장명에 대 한 ProgID (progid htmlfile =) 하드 코딩 다양 한 운영 체제에서 자주 이며.htm 및.html 파일 널리 알려진 및에서 사용 되는 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 배포를 위한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [파일 이름 확장명에 대한 파일 처리기 지정](../extensibility/specifying-file-handlers-for-file-name-extensions.md)