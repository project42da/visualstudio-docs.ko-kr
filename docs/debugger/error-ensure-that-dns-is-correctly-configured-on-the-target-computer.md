---
title: '오류: DNS 대상 컴퓨터에 올바르게 구성 되었는지 확인 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d50eed9a4c769b2e8b58cbdf35c6e10b57ae9b0c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>오류: 대상 컴퓨터에서 DNS가 올바르게 구성되었는지 확인
원격으로 디버깅할 때 다음 오류 메시지가 나타날 수 있습니다.  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 이 오류는 대상 컴퓨터가 Visual Studio 디버거 호스트 컴퓨터의 이름을 확인할 수 없는 경우에 발생합니다. 대상 컴퓨터의 DNS 설정을 확인하십시오.  
  
-   Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 또는 Windows Server 2008 r 2에서 DNS 설정을 확인 하는 방법에 대 한 내용은,이 작업을 수행:에 **시작** 메뉴 선택 **도움말 및 지원** 를 검색할 **TCP/IP 설정 변경**합니다.  
  
-   자세한 내용은 [Microsoft Windows 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=252720) 검색 한 **TCP/IP 설정 변경**합니다.  
  
 DNS 문제를 해결할 수 없는 경우 다른 계정으로 원격 디버거를 실행해 볼 수 있습니다. 이 오류는 로컬 시스템 또는 네트워크 서비스 계정으로 원격 디버거를 실행하는 경우에만 발생합니다. 다른 계정으로 원격 디버거를 실행하는 경우 DNS를 요구하지 않는 NTLM 인증을 사용할 수 있습니다. 이어야 합니다. 프로시저를 참조 하십시오. [오류: 대상 컴퓨터에는 Visual Studio 원격 디버거 서비스가이 컴퓨터에 다시 연결할 수 없습니다](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md)합니다.