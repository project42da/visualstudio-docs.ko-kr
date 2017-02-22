---
title: "파일 이름 확장명에 대 한 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "파일 확장명"
  - "파일 이름 확장명"
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 파일 이름 확장명에 대 한
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

있는 Vspackage의 파일 확장명을 등록 하면 해당 버전으로 연결 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  이 버전의 보다 중요 한 경우입니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 컴퓨터에 설치 되어 있습니다.  
  
 Vspackages에 대 한 파일 확장명 연결 된 프로그래밍 식별자 \(ProgID\)를 가리키는 기본값은 HKEY\_CLASSES\_ROOT 키 아래에 등록 됩니다.  
  
 .Vcproj 파일 확장명에 대 한 등록 정보의 예는 다음과 같습니다.  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 관련 된 파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전의 Progid가 있어야 합니다 등 `VisualStudio.vcproj.8.0`, 병렬 설치 제품 버전 간에 파일 확장명 연결을 유지 하는 제품 수 있도록 합니다.  버전별 ProgID 또한 열기, 편집, 등 고, 덮어쓰기 또는 다른 응용 프로그램이 나 버전으로 덮어쓰는 걱정 없이 표준 동사를 사용할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 특정 한 경우에 파일 확장명과 연관 된 ProgID 변경할 수 없습니다.  예를 들어.htm 파일 확장명에 대 한 ProgID \(progid \= htmlfile\) 다양 한 운영 체제에서 코딩 된 어렵습니다 고 널리 알려진 및 사용에 관련 하 여.htm 및.html 파일입니다.  
  
## 참고 항목  
 [병렬 배포에 대 한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [파일 이름 확장명에 대 한 파일 처리기 지정](../extensibility/specifying-file-handlers-for-file-name-extensions.md)