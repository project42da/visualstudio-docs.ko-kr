---
title: '방법: 숨겨진된 디버거 명령 복원 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, restoring commands
- debugging [Visual Studio], restoring commands
- commands, debugger
ms.assetid: 76ac9b77-f536-43b5-a9fc-984854b1c566
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e48e52f7d838b701745a449b979486b11a708faa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-restore-hidden-debugger-commands"></a>방법: 숨겨진 디버거 명령 복원
Visual Studio를 설치할 때 주 프로그래밍 언어의 기본 IDE 설정 집합을 선택하는 단계가 있습니다. 일부 언어의 기본 IDE 설정에서는 특정 디버거 명령이 표시되지 않을 수 있습니다.  
  
 기본 IDE 설정에 따라 숨겨진 디버거 기능을 사용하려면 다음 절차를 사용하여 명령을 메뉴에 다시 추가해야 합니다.  
  
### <a name="to-restore-hidden-debugger-commands"></a>숨겨진 디버거 명령을 복원하려면  
  
1.  열려 있는 프로젝트는 **도구** 메뉴를 클릭 하 여 **사용자 지정**합니다.  
  
2.  에 **사용자 지정** 대화 상자를 클릭는 **명령을** 탭 합니다.  
  
3.  에 **메뉴 모음:** 드롭다운 목록에서 선택 된 **디버그** 복원 된 명령을 포함 하 고 원하는 메뉴를 합니다.  
  
4.  클릭는 **명령을 추가 중...**  단추입니다.  
  
5.  에 **명령 추가** 상자를 추가 하 고, 클릭 하려는 명령을 선택 **확인**합니다.  
  
6.  다른 명령을 추가하려면 위 단계를 반복합니다.  
  
7.  클릭 **닫기** 모두 메뉴에 명령을 추가 합니다.  
  
    > [!WARNING]
    >  일부 메뉴 항목은 디버거가 실행 모드나 중단 모드 같은 특정 모드에 있을 때만 표시됩니다. 따라서 방금 추가한 항목이 이 단계를 완료한 직후에는 표시되지 않을 수도 있습니다.  
  
## <a name="restoring-commands-not-available-from-the-customize-dialog-box"></a>사용자 지정 대화 상자에서 사용할 수 없는 명령 복원  
 특히 계층 구조 메뉴에 있는 일부 명령에서 복원할 수 없습니다는 **사용자 지정** 대화 상자. 이러한 명령을 복원하려면 IDE 설정의 새 컬렉션을 가져와야 합니다.  
  
#### <a name="to-import-new-ide-settings"></a>새 IDE 설정을 가져오려면  
  
1.  에 **도구** 메뉴를 클릭 하 여 **설정 가져오기 및 내보내기**합니다.  
  
2.  에 **가져오기 및 설정 내보내기 마법사 시작** 페이지 **선택한 환경 설정 가져오기**, 클릭 하 고 **다음**합니다.  
  
3.  에 **현재 설정 저장** 페이지에서를 클릭 하 고 기존의 설정을 저장할지 여부를 결정 **다음**합니다.  
  
4.  에 **가져올 설정 모음 선택** 페이지의 **기본 설정** 폴더를 사용 하려면 명령이 들어 있는 개발 설정의 컬렉션을 선택 합니다. 선택할 수 있는 컬렉션을 알 수 없는 경우 시도 **일반 개발 설정** 또는 **Visual c + + 개발 설정**, 대부분의 디버거 명령을 제공 합니다.  
  
5.  **다음**을 클릭합니다.  
  
6.  에 **가져올 설정을** 페이지의 **옵션**, 있는지 확인 **디버깅** 을 선택 합니다. 함께 가져오려는 설정이 아닌 다른 모든 설정의 확인란은 선택을 해제합니다.  
  
7.  **마침**을 클릭합니다.  
  
8.  에 **가져오기 완료** 페이지에서 설정을 다시 설정와 관련 된 오류를 검토 **세부 정보**합니다.  
  
9. **닫기**를 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [디버거 기본 사항](../debugger/debugger-basics.md)