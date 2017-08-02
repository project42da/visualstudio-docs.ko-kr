---
title: "마법사 (합니다. Vsz) 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .vsz files
- vsz files
- wizards, files
ms.assetid: 72e1d0f3-eef1-455e-b803-96827f030f50
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 3b1ee351d5fbe66a5d74c07c0a7e5a60661d7fcb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/05/2017

---
# <a name="wizard-vsz-file"></a>마법사 (합니다. Vsz) 파일
통합된 개발 환경 (IDE) 마법사를 시작 하려면.vsz 파일을 사용 합니다. 이러한.vsz 파일 IDE 사용 하 여 호출 하는 마법사를 결정 하는 정보와 마법사 전달할 정보를 포함 합니다.  
  
 .Vsz 파일은 없는 섹션이 있는.ini 형식의 텍스트 파일의 버전입니다. IDE에 알려진 정보 파일의 시작 부분에 저장 됩니다. IDE를 호출 하는 마법사 및 IDE에 전달할.vsz 파일에 있는 매개 변수 사이 링크를 제공 합니다. 파일의 나머지 마법사 관련 되어 있으며 IDE에 의해 수집 되 고 특정 마법사에 전달 된 매개 변수를 제공 합니다.  
  
 다음 예제에서는.vsz 파일의 내용을 보여 줍니다.  
  
```  
VSWizard 8.0  
Wizard=VsWizard.CBlankSiteWizard -or- {123-1234556-123334}  
Param="WIZARDNAME = Wizard One"  
Param="WIZARDUI = FALSE"  
```  
  
 다음은.vsz 파일의 파트입니다.  
  
|파트|설명|  
|----------|-----------------|  
|VSWizard|파일에서 첫 번째 매개 변수는 템플릿 파일 형식의 버전입니다. 이 버전 번호는 6.0, 7.0, 7.1 또는 8.0 이어야 합니다. 다른 숫자를 시작할 수 없습니다 및 잘못 된 형식 오류가 발생 합니다.|  
|마법사|이 필드는 OLE의 ProgID 마법사 또는 또는 IDE에 의해 공동으로 만들어집니다 하는 마법사의 CLSID의 GUID 문자열 표현을 포함 합니다.|  
|Param|이러한 파트는 선택 사항입니다. 필요한 만큼 추가할 수 있습니다.|  
  
 매개 변수 설정 하 여.vsz 파일 마법사 추가 사용자 지정 매개 변수를 전달 합니다. 각 값 마법사 variant의 배열에서 문자열 요소 변수로 전달 됩니다. 자세한 내용은 참조 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)합니다. 사용자 지정 마법사의 개발에서.vsz 파일을 사용 하는 방법에 대 한 정보를 참조 하십시오. [합니다. Vsz 파일 (프로젝트 컨트롤)](/cpp/ide/dot-vsz-file-project-control)  
  
 기본 로캘 ID.vsz 파일을 추가 하려면 `FALLBACK_LCID`= xxxx는 로캘 ID, 영어의 경우 1033 예를 들어 xxxx 합니다. 때 `FALLBACK_LCID` 매개 변수를 정의 현재 ID을 찾을 수 없는 경우 마법사에서 제공 된 대체 로캘 ID를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [템플릿 디렉터리 설명(.Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)
