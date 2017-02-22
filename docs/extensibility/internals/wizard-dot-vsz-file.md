---
title: "마법사 (합니다. Vsz) 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".vsz 파일"
  - "vsz 파일"
  - "마법사 파일"
ms.assetid: 72e1d0f3-eef1-455e-b803-96827f030f50
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 마법사 (합니다. Vsz) 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

통합된 개발 환경 \(IDE\).vsz 파일을 사용 하 여 마법사를 시작 합니다.  .Vsz 파일 IDE를 사용 하 여 호출 하는 마법사를 결정 하는 정보 및 마법사에 전달할 정보를 포함 합니다.  
  
 .Vsz 파일은.ini 형식의 텍스트 파일 섹션이 없습니다. 한 버전입니다.  IDE로 알려진 정보는 파일의 시작 부분에 저장 됩니다.  IDE를 호출 하는 마법사와 IDE로 전달 되어야 하는.vsz 파일에 있는 매개 변수 사이 연결을 제공 합니다.  나머지 파일은 마법사에 따라 다릅니다 및 IDE에서 수집 되 고 특정 마법사에 전달할 매개 변수를 제공 합니다.  
  
 다음은.vsz 파일의 내용을 보여 줍니다.  
  
```  
VSWizard 8.0  
Wizard=VsWizard.CBlankSiteWizard -or- {123-1234556-123334}  
Param="WIZARDNAME = Wizard One"  
Param="WIZARDUI = FALSE"  
```  
  
 다음은.vsz 파일의 부품입니다.  
  
|파트|설명|  
|--------|--------|  
|VSWizard|첫 번째 매개 변수는 파일에서은 템플릿 파일 형식의 버전 번호입니다.  이 버전 번호는 6.0, 7.0, 7.1, 또는 8.0 있어야 합니다.  다른 숫자를 시작할 수 없습니다 및 잘못 된 형식 오류.|  
|마법사|이 필드에는 OLE ProgID에서 마법사의 또는 또는 IDE에서 cocreated 됩니다 마법사의 CLSID의 GUID 문자열 표현 중 포함 되어 있습니다.|  
|Param|이러한 파트는 선택 사항입니다.  필요한 만큼 추가할 수 있습니다.|  
  
 매개 변수는.vsz 파일이 추가 사용자 지정 매개 변수를 마법사에 전달할 수 있습니다.  각 값 변형 배열의 문자열 요소로 마법사에 전달 됩니다.  자세한 내용은 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)를 참조하십시오.  사용자 지정 마법사의.vsz 파일을 사용 하는 방법에 대 한 내용은 참조 하십시오.[.Vsz 파일\(프로젝트 컨트롤\)](/visual-cpp/ide/dot-vsz-file-project-control)  
  
 .Vsz 파일에는 기본 로캘 ID를 추가 하려면 지정 합니다. `FALLBACK_LCID`\= xxxx xxxx는 로캘 ID 1033 영어에 대 한 예를 들어.  때 `FALLBACK_LCID` 매개 변수가 정의 되 면 현재 ID를 찾을 수 없는 경우 마법사는 제공 된 대체 로케일 ID 사용 합니다.  
  
## 참고 항목  
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [서식 파일 디렉터리 설명 \(합니다. Vsdir\) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)