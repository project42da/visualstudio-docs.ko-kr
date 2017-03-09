---
title: "Resources &#39;file1&#39; and &#39;file2&#39; have the same manifest resource name &#39;name&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.resource_naming_conflict"
ms.assetid: 50d656ad-8557-4240-95b0-3f44b9c21da6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Resources &#39;file1&#39; and &#39;file2&#39; have the same manifest resource name &#39;name&#39;
프로젝트 시스템에서 `BuildAction` 속성이 `EmbeddedResource`로 설정되어 있고 중립 문화권을 갖는 두 파일에 대해 동일한 어셈블리 리소스 이름이 계산되었습니다.  이 오류가 발생하면 빌드 프로세스는 실패합니다.  `BuildAction` 속성에 대한 자세한 내용은 [File Properties](http://msdn.microsoft.com/ko-kr/013c4aed-08d6-4dce-a124-ca807ca08959)을 참조하십시오.  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 폴더 기반 네임스페이스를 사용하지 않으므로 다음과 같은 리소스 파일 이름을 사용하면  
  
-   Proj1\\FolderA\\MyProj.bmp  
  
-   Proj1\\FolderB\\MyProj.bmp  
  
 두 파일 모두에 대해 Proj1.MyProj.bmp라는 어셈블리 매니페스트 이름이 만들어집니다.  
  
 **이 오류를 해결하려면**  
  
-   이 오류를 해결하려면 해당 리소스 파일\(*file1*과 *file2*\)의 이름을 바꾸십시오.  
  
## 참고 항목  
 [NIB: Resource File Naming Conventions](http://msdn.microsoft.com/ko-kr/7b1a2cdf-6196-4034-8fc7-51a271842cc2)