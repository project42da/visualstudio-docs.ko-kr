---
title: "격리 셸 사용 하 여 수정 된 합니다. Pkgundef 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgundef file
ms.assetid: 9cee2a20-f8ac-4d9d-aef9-068fcd9f27a4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7f863377f326dd7bd62381a34c6236d938b11505
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgundef-file"></a>격리 셸 사용 하 여 수정 된 합니다. Pkgundef 파일
격리 셸 응용 프로그램에서 지정 된 레지스트리 항목을 제외.pkgundef 파일을 수정할 수 있습니다. 일반적으로 컴퓨터에서 응용 프로그램을 시작 하는 처음으로 Visual Studio shell 기존 Visual Studio 레지스트리 항목에 복사 응용 프로그램에 대 한 루트 레지스트리 키 합니다. 현재 설치 된 Vspackage에 대 한 참조가 포함 됩니다.  
  
 격리 셸 응용 프로그램에서 특정 레지스트리 항목을 제외 하려면 패키지 키 항목에 의해 다음 응용 프로그램.pkgundef 파일에 추가 합니다. 키 및 항목에서.pkgdef 파일에서와 마찬가지로 표시 됩니다. 즉, [$RootKey $] 또는 [$RootKey$\\*하위 키*] 및 "*항목*" =*값*여기서 *하위 키* 하위 키에 영향을 줄은 *항목* 항목은 항목을 제거 하려면 및 *값* 있거나 `""` 또는 `dword:00000000`합니다.  
  
 레지스트리 키에서 여러 항목을 제외 하려면 방금 나열 키 한 번 제외할 각 항목에 대 한 줄씩 합니다.  
  
 격리 셸 응용 프로그램에서 전체 레지스트리 키를 제외 하려면 응용 프로그램.pkgundef 파일에 키를 추가 하지만 그 키에 대 한 레지스트리 항목을 지정 하지 마십시오.  
  
 .Pkgundef 파일에 주석을 추가할 수 있습니다. 한 줄 주석 처음 두 문자 슬래시 두 개 있어야 합니다.  
  
 예를 들어, 제거 하는 **연결할 데이터베이스** 및 **Serve r에 연결** 에 있는 명령을 **도구** 메뉴 줄의 주석 처리 제거:  
  
```  
[$RootKey$\Packages\{8D8529D3-625D-4496-8354-3DAD630ECC1B}]  
```  
  
 줄을 추가 합니다.  
  
```  
[$RootKey$\Packages\{198E76C1-34C0-424D-9957-B3EBD80265FB}]  
```  
  
 응용 프로그램의.pkgundef 파일입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 기능 패키지 Guid](package-guids-of-visual-studio-features.md)   
 [격리 셸 사용자 지정](customizing-the-isolated-shell.md)