---
title: 소스 열거 명령 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d21a18a58832918b566e925c7c3898988740a1a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="list-source-command"></a>소스 목록 표시 명령
소스 코드의 지정된 줄을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>스위치  
 /Count:`number`  
 선택 사항입니다. 표시할 줄 수를 지정합니다.  
  
 /Current  
 선택 사항입니다. 현재 줄을 표시합니다.  
  
 /File:`filename`  
 선택 사항입니다. 표시할 파일의 경로입니다. 파일 이름이 지정되지 않은 경우 이 명령은 현재 문의 줄에 대한 소스 코드를 표시합니다.  
  
 /Line:`number`  
 선택 사항입니다. 특정 줄 번호를 표시합니다.  
  
 /ShowLineNumbers:`yes|no`  
 선택 사항입니다. 줄 번호를 표시할지 여부를 지정합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예  
 이 예제에서는 줄 번호를 표시하여 Form1.vb 파일의 줄 4 소스 코드를 나열합니다.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)