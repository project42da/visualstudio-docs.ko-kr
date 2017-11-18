---
title: "SDI 서버 응용 프로그램 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 089eeada5f3d9d392aff7768ed3f5b813ef8f772
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sdi-server-applications"></a>SDI 서버 응용 프로그램
지정 해야 SDI 서버 응용 프로그램 디버깅 하는 경우, `/Embedding` 또는 `/Automation` 에 **명령줄 인수** 속성에는 *프로젝트* C/c + +, C#에 대 한 속성 페이지 대화 상자 또는 Visual Basic 프로젝트입니다.  
  
 이 명령줄 인수를 사용하면 컨테이너에서 실행하는 것처럼 디버거에서 서버 응용 프로그램을 실행할 수 있습니다. 그런 다음 프로그램 관리자나 파일 관리자에서 컨테이너를 시작하면 컨테이너는 디버거에서 시작된 서버 인스턴스를 사용합니다.  
  
## <a name="finding-the-command-line-arguments-property"></a>명령줄 인수 속성 찾기  
 액세스는 *프로젝트* 속성 페이지 대화 상자 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 바로 가기 메뉴에서 속성을 선택 합니다. 명령줄 인수 속성을 찾으려면 구성 속성 범주를 확장하고 디버깅 페이지를 클릭하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [COM 및 ActiveX 디버깅](../debugger/com-and-activex-debugging.md)   
 [방법: COM 서버 디버그](../debugger/how-to-debug-com-servers.md)