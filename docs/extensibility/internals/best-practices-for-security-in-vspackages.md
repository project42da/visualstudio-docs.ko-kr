---
title: "Vspackage에서 보안의 모범 사례 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: c7ceb884ad060ea45c0fd204b5611ce284d3d2af
ms.lasthandoff: 02/22/2017

---
# <a name="best-practices-for-security-in-vspackages"></a>Vspackage에서 보안 모범 사례
설치 하는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 컴퓨터에 관리 자격 증명으로 컨텍스트 실행 되어야 합니다. 보안 및 배포의 기본 단위는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 응용 프로그램은는 [Vspackage](../../extensibility/internals/vspackages.md)합니다. VSPackage를 사용 하 여 등록 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 관리자 자격 증명이 있는 필요 합니다.  
  
 관리자 권한이 부여 레지스트리 및 파일 시스템에 작성 하 고 코드를 실행 합니다. 개발, 배포 또는 VSPackage를 설치 하려면 이러한 권한이 있어야 합니다.  
  
 를 설치 하는 즉시 VSPackage은 완전히 신뢰할 수 있습니다. VSPackage와 연관 된 권한이 높은 수준으로 인해 실수로 악의적인 의도로 포함 된 VSPackage를 설치 하는 것이 같습니다.  
  
 사용자가 Vspackage 신뢰할 수 있는 원본 에서만에서 설치를 확인 해야 합니다. 강력한 이름 지정 되 고 서명 해야 Vspackage 개발 회사, 되도록 사용자는 변조 방지 됩니다. Vspackage를 개발 하는 회사 웹 서비스 및 평가 하 고 보안 문제를 해결 하려면 원격 설치와 같은 해당 외부 종속성을 검사 해야 합니다.  
  
 자세한 내용은.NET Framework에 대 한 보안 코딩 지침 참조 ([http://msdn.microsoft.com/library/d55zzx87.aspx](http://msdn.microsoft.com/library/d55zzx87.aspx)).  
  
## <a name="see-also"></a>참고 항목  
 [추가 기능 보안](http://msdn.microsoft.com/Library/44a5c651-6246-4310-b371-65378917c799)   
 [DDEX 보안](http://msdn.microsoft.com/en-us/44a52a70-5c98-450e-993d-4a3b32f69ba8)
