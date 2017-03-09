---
title: "VSInstr 경고 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "계측, VSInstr 도구"
  - "성능 도구, VSInstr 도구"
  - "VSInstr 도구"
  - "경고"
  - "경고, VSInstr 도구"
ms.assetid: 47512bc9-a8e9-4628-883a-d9888edab786
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VSInstr 경고
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 표는 VSInstr.exe 도구에 의해 발생되는 경고를 나열합니다.  경고 번호에 NOWARN 옵션을 사용하면 경고가 나타나지 않도록 할 수 있습니다.  
  
|경고 번호|설명|  
|-----------|--------|  
|**VSP2000**|내부 오류입니다.  이 실행 파일에 대한 모듈 파일 이름을 가져올 수 없습니다.|  
|**VSP2001**|\<assembly name\>은\(는\) 강력한 이름의 어셈블리입니다.  실행하기 전에 다시 서명해야 합니다.<br /><br /> 이 경고는 서명된 어셈블리가 계측되었을 때 발생합니다.  sn.exe 도구를 사용하여 이진을 포기하거나 강력한 이름 요구 사항을 일시적으로 끌 수 있습니다.  자세한 내용은 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)을 참조하십시오.|  
|**VSP2002**|\<filename\> 파일에서 \<funcname\> 함수를 찾을 수 없습니다.<br /><br /> 이 경고는 지정한 파일에서 함수를 찾을 수 없을 때 발생합니다.|  
|**VSP2003**|\<filename\> 파일에서 \<funcname\> in file \<filename\> 함수로의 크로스 점프를 찾을 수 없습니다.<br /><br /> 이 경고는 VSInstr에서 크로스 점프를 취소할 수 없을 때 발생합니다.  크로스 점프는 코드 최적화에 사용됩니다.|  
|**VSP2004**|\<funcname\> 함수가 EXCLUDE 명령줄 스위치를 통해 제외되었지만 이 함수에 크로스 점프가 들어 있으므로 필요합니다.<br /><br /> 이 경고는 EXCLUDE 옵션을 통해 함수가 제외되었지만 계측 프로세스 중에 이 함수가 필요한 경우 발생합니다.  프로파일러가 필요한 함수를 자동으로 포함시킵니다.|  
|**VSP2005**|내부 계측 오류 \<error text\><br /><br /> 이 경고는 계측을 수행할 수 없을 때 발생합니다.  오류 텍스트를 검토하여 수정할 수 있는지 확인합니다.|  
|**VSP2006**|\<name\>의 PDB를 찾을 수 없습니다.<br /><br /> 이 경고는 PDB 파일이 검색 경로에 없거나 해당 이진과 일치하지 않는 경우 발생합니다.|  
|**VSP2007**|\<filename\>에 계측 가능한 코드가 없습니다.<br /><br /> 이 경고는 이진 파일의 함수가 모두 제외되었거나 지정한 파일에만 리소스가 포함된 경우 발생합니다.|  
|**VSP2008**|\<name\> 보안 특성을 가져올 수 없습니다.  code \<code\>오류 코드<br /><br /> 이 경고는 사용자에게 READ\_DAC 권한이 없는 경우 발생합니다.  계측 프로세스 중에 프로파일러는 이진에 대한 원래 DACL을 유지하려고 합니다.  원래 이진은 새 이진으로 교체되므로 원래 이진의 DACL을 복사하여 새 이진에 적용해야 합니다.  하지만 사용자에게 원래 이진에 대한 READ\_DAC 액세스 권한이 없으면 이 작업이 실패합니다.|  
|**VSP2009**|\<name\>에 보안 특성을 설정할 수 없습니다.  오류 코드 \<name\><br /><br /> 이 경고는 사용자에게 WRITE\_DAC 권한이 없는 경우 발생합니다.  계측 프로세스 중에 프로파일러는 이진에 대한 원래 DACL을 유지하려고 합니다.  원래 이진은 새 이진으로 교체되므로 원래 이진의 DACL을 복사하여 새 이진에 적용해야 합니다.  하지만 사용자에게 새 이진에 대한 WRITE\_DAC 액세스 권한이 없으면 이 작업이 실패합니다.|  
|**VSP2010**|\-INCLUDE\/\-EXCLUDE 옵션 때문에 계측하기 위해 선택한 함수가 없습니다.|  
|**VSP2011**|Include\/Exclude funcspec \<name\>이 다른 함수와 일치하지 않습니다.|  
|**VSP2012**|이미지에 코드 검사를 계측할 수 있는 코드가 없습니다.<br /><br /> 프로파일러는 다음 유형의 코드를 계측하지 않습니다.<br /><br /> -   정적 CRT 함수<br />-   NonUserCodeAttribute 특성이 지정된 관리 메서드<br />-   DebuggerHiddenAttribute 특성이 지정된 관리 메서드<br />-   MASM 블록<br /><br /> 이 경고는 이 필터링 후 남은 코드가 없는 경우 생성됩니다.|  
|**VSP2013**|이 이미지를 계측하려면 32비트 프로세스로 실행해야 합니다.  이를 반영하기 위해 CLR 헤더 플래그가 업데이트되었습니다.<br /><br /> 프로파일러는 64비트 운영 체제에서 WOW64 에뮬레이터에 32비트 프로세스를 열 수 있도록 이진을 수정합니다.  라이브러리\(DLL\)의 경우, 기존 64비트 프로세스에서 로드된 경우에는 실패합니다.  이 경고는 사용자에게 종속성을 알립니다.|  
|**VSP2014**|결과로 나오는 계측된 이미지가 잘못 표시되어 실행되지 않을 수 있습니다.<br /><br /> 이 메시지는 최종 계측된 어셈블리에 잘못된 PE 헤더가 있을 때 발생합니다.|  
  
## 참고 항목  
 [VSInstr](../profiling/vsinstr.md)