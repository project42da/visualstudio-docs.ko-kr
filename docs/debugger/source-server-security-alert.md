---
title: "서버 보안 경고 원본 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7eb50bec1967b9c1f7a969eb802888864f5e72eb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="source-server-security-alert"></a>소스 서버 보안 경고
소스 서버를 사용할 경우 알 수 있고 신뢰할 수 있는 위치의 기호 파일만 사용합니다.  
  
 이 경고는 소스 서버 지원을 사용하는 경우에 나타납니다. 소스 서버 명령은 디버그 기호 파일에 포함 되어 (***.pdb** 파일). PDB 파일의 출처를 확인해야 합니다.  
  
> [!IMPORTANT]
>  소스 서버를 사용할 때는 잠재적인 보안 위협을 고려해야 합니다. 예를 들어, 임의의 명령이 응용 프로그램의 PDB 파일에 포함될 수 있으므로 실제로 실행하려는 명령만 srcsrv.ini 파일에 추가하도록 주의해야 합니다. srcsvr.ini 파일에 포함되지 않은 명령을 실행하려고 하면 확인 대화 상자가 나타납니다. 자세한 내용은 참조 [보안 경고: 디버거가 명령을 실행 해야 신뢰할 수 없는](../debugger/security-warning-debugger-must-execute-untrusted-command.md)합니다. 명령 매개 변수 없음 유효성 검사를 수행 하 고 신뢰할 수 있는 명령에 대해 주의 기울여야 합니다. 예를 들어 cmd.exe를 신뢰한 경우 악의적인 사용자가 이 명령을 위험하게 만드는 매개 변수를 지정할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [디버거 보안](../debugger/debugger-security.md)   
 [원본 서버](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)