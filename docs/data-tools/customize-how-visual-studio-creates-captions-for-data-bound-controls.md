---
title: Visual Studio의 데이터 바인딩된 컨트롤에 대 한 캡션을 만드는 방법을 사용자 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- Label captions, Data Sources window
- smart captions
- captions, data-bound
- Data Sources Window, label captions
ms.assetid: 6d4d15f8-4d78-42fd-af64-779ae98d62c8
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 031301edc2fbf0c9acc08f92d3324160dd5383cf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="customize-how-visual-studio-creates-captions-for-data-bound-controls"></a>Visual Studio의 데이터 바인딩된 컨트롤에 대 한 캡션을 만드는 방법을 사용자 지정
항목을 끌면는 [데이터 소스 창](add-new-data-sources.md) 디자이너에 특별 한 고려 질문과 관련 하 여: 캡션 레이블의 열 이름을 두 보다 읽기 쉬운 문자열로 변경 또는 되도록 개 이상의 단어가 서로 연결 됩니다. 이러한 레이블을 설정 하 여 만든 하는 방법을 사용자 지정할 수 있습니다는 **SmartCaptionExpression**, **SmartCaptionReplacement**, 및 **SmartCaptionSuffix** 값 **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Data 디자이너** 레지스트리 키입니다.  
  
> [!NOTE]
> 이 레지스트리 키를 만들 때까지 존재 하지 않습니다.  
  
값에 입력 한 정규식에 의해 제어 됩니다 스마트 캡션는 **SmartCaptionExpression** 값입니다. 추가 **데이터 디자이너** 레지스트리 키에 기본 정규식 캡션 레이블을 제어 하는 보다 우선 합니다. 정규식에 대 한 자세한 내용은 참조 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)합니다.  
  
다음 표에서 캡션 레이블을 제어 하는 레지스트리 값을 설명 합니다.  
  
|레지스트리 항목|설명|  
|-------------------|-----------------|  
|**SmartCaptionExpression**|패턴에 일치 시키는 데 사용할 정규식입니다.|  
|**SmartCaptionReplacement**|형식에서 일치 하는 모든 그룹을 표시 하는 **SmartCaptionExpression**합니다.|  
|**SmartCaptionSuffix**|캡션의 끝에 추가 하는 선택적 문자열.|  
  
다음 표에서 이러한 레지스트리 값에 대 한 내부 기본 설정을 나열합니다.  
  
|레지스트리 항목|기본값|설명|  
|-------------------|-------------------|-----------------|  
|**SmartCaptionExpression**|(\\\p{Ll}) (\\\p{Lu})&#124;_ +|소문자 대문자 문자 또는 밑줄 문자를 찾습니다.|  
|**SmartCaptionReplacement**|$1 $2|$1 식의 첫 번째 괄호로 일치 하는 문자를 나타내고 $2의 두 번째 괄호에 일치 하는 문자를 나타냅니다. 대신 일치 하는 첫 번째, 공백 하나 및 일치 하는 두 번째에 있습니다.|  
|**SmartCaptionSuffix**|:|반환된 된 문자열에 추가 되는 문자를 나타냅니다. 예를 들어, 캡션이 `Company Name`, 접미사를 사용 하면 `Company Name:`|  
  
> [!CAUTION]
> 레지스트리 편집기에서 작업을 수행 하는 경우에 매우 주의 해야 합니다. 편집 하기 전에 레지스트리를 백업 합니다. 레지스트리 편집기를 잘못 사용 하면 운영 체제를 다시 설치 해야 하는 심각한 문제가 발생할 수 있습니다. Microsoft은 레지스트리 편집기를 잘못 사용 하 여 발생 하는 문제를 해결할 수 있음을 보장 하지 않습니다. 레지스트리 편집기 사용에 따른 결과는 사용자의 책임입니다.  
>   
>  다음 기술 자료 문서를 백업, 편집 및 레지스트리 복원에 대 한 지침이 포함 되어: [Microsoft Windows 레지스트리 설명](http://support.microsoft.com/default.aspx?scid=kb;en-us;256986) (http://support.microsoft.com/default.aspx?scid=kb; en-us; 256986)  
  
### <a name="to-modify-the-smart-captioning-behavior-of-the-data-sources-window"></a>데이터 소스 창에서의 스마트 캡션 동작을 수정 하려면  
  
1.  클릭 하 여 명령 창을 열고 **시작** 차례로 **실행**합니다.  
  
2.  형식 `regedit` 에 **실행** 대화 상자와 클릭 **확인**합니다.  
  
3.  확장 된 **HKEY_CURRENT_USER**, **소프트웨어*, **Microsoft**, **VisualStudio** 노드.  
  
7.  마우스 오른쪽 단추로 클릭는 **15.0** 노드를 새 고 **키** 라는 `Data Designers`합니다.  
  
8.  마우스 오른쪽 단추로 클릭는 **데이터 디자이너** 노드를 3 개의 새 문자열 값을 만듭니다.

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`
  
11. 마우스 오른쪽 단추로 클릭는 **SmartCaptionExpression** 값을 선택 **수정**합니다.  
  
12. 원하는 정규식 입력는 **데이터 원본** 사용 하는 창입니다.  
  
13. 마우스 오른쪽 단추로 클릭는 **SmartCaptionReplacement** 값을 선택 **수정**합니다.  
  
14. 교체를 입력 합니다. 정규식에 일치 하는 패턴을 원하는 방식으로 형식이 지정 된 문자열입니다.  
  
15. 마우스 오른쪽 단추로 클릭는 **SmartCaptionSuffix** 값을 선택 **수정**합니다.  
  
16. 캡션의 끝에 표시할 모든 문자를 입력 합니다.  
  
    항목을 끌어 다음에 **데이터 소스** 창에서 캡션 레이블이 만들어집니다 제공 된 새 레지스트리 값을 사용 하 여 합니다.  
  
### <a name="to-turn-off-the-smart-captioning-feature"></a>스마트 캡션 기능 해제 하려면  
  
1.  클릭 하 여 명령 창을 열고 **시작** 차례로 **실행**합니다.  
  
2.  형식 `regedit` 에 **실행** 대화 상자와 클릭 **확인**합니다.  
  
3.  확장 된 **HKEY_CURRENT_USER**, **소프트웨어**, **Microsoft**, **VisualStudio** 노드.  
  
7.  마우스 오른쪽 단추로 클릭는 **15.0** 노드를 새 고 **키** 라는 `Data Designers`합니다.  
  
8.  마우스 오른쪽 단추로 클릭는 **데이터 디자이너** 노드를 3 개의 새 문자열 값을 만듭니다.

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`
  
11. 마우스 오른쪽 단추로 클릭는 **SmartCaptionExpression** 선택한 항목을 **수정**합니다.  
  
12. 입력 `(.*)` 값에 대 한 합니다. 이 전체 문자열을 일치 합니다.  
  
13. 마우스 오른쪽 단추로 클릭는 **SmartCaptionReplacement** 선택한 항목을 **수정**합니다.  
  
14. 입력 `$1` 값에 대 한 합니다. 이 문자열을 변경 되지 않도록 하는 전체 문자열은 일치 하는 값을 바꿉니다.  
  
    항목을 끌어 다음에 **데이터 소스** 창의 캡션 레이블이 수정 되지 않은 캡션을 사용 하 여 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
[Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)