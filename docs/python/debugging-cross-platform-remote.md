---
title: "Visual Studio에서 Python 플랫폼 간 원격 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 4/4/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa667357-763f-4ce6-8e47-48f9337658a8
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 85576806818a6ed289c2f660f87b5c419016c600
ms.openlocfilehash: fa3d69cbb34a61a327d0b4c27430ff04b670a568
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---

# <a name="remotely-debugging-python-code"></a>Python 코드 원격 디버깅

Visual Studio는 Windows 컴퓨터에서 Python 응용 프로그램을 로컬 및 원격으로 시작하고 디버그할 수 있습니다([Remote Debugging](../debugger/remote-debugging.md)(원격 디버깅) 참조). 또한 [ptvsd 라이브러리](https://pypi.python.org/pypi/ptvsd)를 사용하여 CPython 이외의 다른 운영 체제, 장치 또는 Python 구현에서 원격으로 디버그할 수도 있습니다.

ptvsd를 사용하는 경우 디버그되는 Python 코드는 Visual Studio에서 연결할 수 있는 디버그 서버를 호스팅합니다. 이렇게 하려면 서버를 가져오고 사용할 수 있도록 코드를 약간 수정해야 하며, TCP 연결을 허용하기 위해 원격 컴퓨터에 네트워크 또는 방화벽 구성이 필요할 수 있습니다.

원격 디버깅에 대한 소개는 [자세히 알아보기: 플랫폼 간 원격 디버깅](https://youtu.be/y1Qq7BrV6Cc)(youtube.com, 6분 22초)을 참조하세요.

> [!VIDEO https://www.youtube.com/embed/y1Qq7BrV6Cc]

## <a name="setting-up-a-linux-machine"></a>Linux 컴퓨터 설정

이 연습을 수행하려면 다음이 필요합니다.

- Mac OSX 또는 Linux와 같은 운영 체제에서 Python을 실행하는 원격 컴퓨터.
- 원격 디버깅의 기본값으로 해당 컴퓨터의 방화벽에서 열려 있는 포트 5678(인바운드).

쉽게 [Azure에서 Linux 가상 컴퓨터](https://docs.microsoft.com/azure/virtual-machines/linux/creation-choices)를 만들고 Windows에서 [원격 데스크톱을 사용하여 Linux 가상 컴퓨터에 액세스](https://docs.microsoft.com/azure/virtual-machines/linux/use-remote-desktop)할 수 있습니다. Python이 기본적으로 설치되어 있으므로 VM에 Ubuntu를 사용하면 편리합니다. 그렇지 않은 경우 추가 Python 다운로드 위치는 [원하는 Python 인터프리터 설치](python-environments.md#selecting-and-installing-python-interpreters)를 참조하세요.

Azure VM에 대한 방화벽 규칙을 만드는 방법에 대한 자세한 내용은 [Azure Portal을 사용하여 Azure에서 VM으로 포트 열기](https://docs.microsoft.com/azure/virtual-machines/windows/nsg-quickstart-portal)를 참조하세요.

## <a name="preparing-the-script-for-debugging"></a>디버그할 스크립트 준비

1. 원격 컴퓨터에서 다음 코드를 사용하여 `guessing-game.py`라는 Python 파일을 만듭니다.

  ```python
    import random

    guesses_made = 0
    name = input('Hello! What is your name?\n')
    number = random.randint(1, 20)
    print('Well, {0}, I am thinking of a number between 1 and 20.'.format(name))

    while guesses_made < 6:
    guess = int(input('Take a guess: '))
    guesses_made += 1
    if guess < number:
        print('Your guess is too low.')
    if guess > number:
        print('Your guess is too high.')
    if guess == number:
        break
    if guess == number:
    print('Good job, {0}! You guessed my number in {1} guesses!'.format(name, guesses_made))
    else:
    print('Nope. The number I was thinking of was {0}'.format(number))
  ```
 
1. `pip3 install ptvsd`를 사용하여 사용자 환경에 `ptvsd` 패키지를 설치합니다. (참고: 문제 해결에 필요한 경우를 대비하여 ptvsd 버전을 기록해 두는 것이 좋습니다. [ptvsd 목록](https://pypi.python.org/pypi/ptvsd)은 사용 가능한 버전도 보여 줍니다.)

1. `guessing-game.py`에서 가능한 가장 빠른 지점에 다른 코드보다 먼저 해당 코드를 추가하여 원격 디버깅을 사용하도록 설정합니다. (엄격한 요구 사항은 아니지만, `enable_attach` 함수를 호출하기 전에 생성된 모든 백그라운드 스레드를 디버그할 수는 없습니다.)

   ```python
   import ptvsd
   ptvsd.enable_attach('my_secret')
   ```

   `enable_attach`(“암호”라고 함)에 전달되는 첫 번째 인수는 실행 중인 스크립트에 대한 액세스를 제한하고 사용자는 원격 디버거를 연결할 때 이 암호를 입력하게 됩니다. (권장되지는 않지만, `enable_attach(secret=None)`를 사용하여 모든 사용자가 연결할 수 있도록 허용할 수 있습니다.)

1. 파일을 저장하고 `python3 guessing-game.py`를 실행합니다. `enable_attach`에 대한 호출이 백그라운드에서 실행되고, 달리 프로그램과 상호 작용하지 않으면 들어오는 연결을 기다립니다. 원하는 경우 디버거가 연결될 때까지 `enable_attach` 뒤에 `wait_for_attach` 함수를 호출하여 프로그램을 차단할 수 있습니다.

> [!Tip]
> `enable_attach` 및 `wait_for_attach` 외에도, ptvsd는 디버거가 연결되어 있으면 중단점을 프로그래밍 방식으로 작동하는 `break_into_debugger` 도우미 함수를 제공합니다. 또한 디버거가 연결되어 있으면 `True`를 반환하는 `is_attached` 함수도 있지만, 다른 `ptvsd` 함수를 호출하기 전에 이 결과를 확인할 필요가 없습니다.

## <a name="attaching-remotely-from-python-tools"></a>Python 도구에서 원격으로 연결

이 단계에서는 간단한 중단점을 설정하여 원격 프로세스를 중지합니다.

1. 로컬 컴퓨터에 원격 파일의 복사본을 만들고 Visual Studio에서 엽니다. 파일의 위치는 중요하지 않지만, 이름은 연결될 원격 컴퓨터의 스크립트 이름과 일치해야 합니다.

1. (선택 사항) 로컬 컴퓨터에 ptvsd에 대한 IntelliSense를 두려면 Python 환경에 ptvsd 패키지를 설치합니다.

1. **디버그 > 프로세스에 연결**을 선택합니다.

1. 나타나는 **프로세스에 연결** 대화 상자에서 **연결 형식**을 **Python remote (ptvsd)**(Python 원격(ptvsd))로 설정합니다. (이전 버전의 Visual Studio에서는 이름이 **전송** 및 **Python 원격 디버깅**이었습니다.)

1. **연결 대상** 필드(이전 버전의 경우 **한정자**)에 `tcp://<secret>@<ip_address>:5678`을 입력합니다. 여기서 `<secret>`은 Python 코드에서 전달된 문자열 `enable_attach`이고, `<ip_address>`는 원격 컴퓨터의 IP 주소이며(명시적 주소 또는 myvm.cloudapp.net과 같은 이름일 수 있음), `:5678`은 원격 디버깅 포트 번호입니다.

    > [!Warning]
    > 공용 인터넷으로 연결하는 경우 `tcps`를 대신 사용하고 [SSL로 디버거 연결 보안](#securing-the-debugger-connection-with-ssl)에 대한 아래 지침을 따라야 합니다.

1. Enter 키를 눌러 해당 컴퓨터에서 사용할 수 있는 ptvsd 프로세스의 목록을 채웁니다.

    ![연결 대상 입력 및 프로세스 나열](~/python/media/remote-debugging-qualifier.png)

    이 목록을 채운 후 원격 컴퓨터에서 다른 프로그램을 시작하게 되는 경우 **새로 고침** 단추를 선택합니다.

1. 디버그할 프로세스를 선택한 다음 **연결**을 선택하거나 프로세스를 두 번 클릭합니다.

1. 그러면 스크립트가 원격 컴퓨터에서 계속 실행되는 동안 Visual Studio에서 디버깅 모드로 전환하여 모든 일반적인 [디버깅](debugging.md) 기능을 제공합니다. 예를 들어 `if guess < number:` 줄에 중단점을 설정한 다음 원격 컴퓨터로 전환하고 다른 guess를 입력합니다. 이렇게 하고 나면 로컬 컴퓨터의 Visual Studio가 해당 중단점에서 중지하고 로컬 변수 등을 보여 줍니다.

    ![적중된 중단점](~/python/media/remote-debugging-breakpoint-hit.png)

1. 디버깅을 중지하면 Visual Studio는 원격 컴퓨터에서 계속 실행되는 프로그램에서 분리됩니다. 또한 ptvsd는 계속 디버거 연결을 수신 대기하므로 언제든지 프로세스에 다시 연결할 수 있습니다.

1. 원격 프로그램을 중지하면 Visual Studio가 자동으로 디버거를 분리하지 않습니다. 

### <a name="connection-troubleshooting"></a>연결 문제 해결

1. **연결 형식**에 대해 **Python remote (ptvsd)**(Python 원격(ptvsd))를 선택했는지 확인합니다(이전 버전의 경우 **전송**에 대해 **Python 원격 디버깅**).
1. **연결 대상**(또는 **한정자**)의 암호가 원격 코드의 암호와 정확히 일치하는지 확인합니다.
1. **연결 대상**(또는 **한정자**)의 IP 주소가 원격 컴퓨터의 IP 주소와 일치하는지 확인합니다.
1. 원격 컴퓨터에서 원격 디버깅 포트를 열었는지와 연결 대상에 `:5678`과 같은 포트 접미사를 포함했는지 확인합니다.
    - 다른 포트를 사용해야 하는 경우 `ptvsd.enable_attach(secret = 'my_secret', address = ('0.0.0.0', 8080))`에서처럼 `enable_attach` 호출에서 `address` 인수를 사용하여 지정할 수 있습니다. 이 경우 방화벽에서 해당 특정 포트를 엽니다.
1. `pip3 list`로 반환된, 원격 컴퓨터에 설치된 ptvsd 버전이 Visual Studio에서 사용 중인 Python 도구 버전에서 사용되는 ptvsd 버전과 일치하는지 아래 표에서 확인합니다. 필요한 경우 원격 컴퓨터에서 ptvsd를 업데이트합니다.

    | Visual Studio 버전 | Python 도구/ptvsd 버전 |
    | --- | --- |
    | 2017 | 3.0.0 |
    | 2015 | 2.2.6 |
    | 2013 | 2.2.2 |
    | 2012, 2010 | 2.1 |


## <a name="securing-the-debugger-connection-with-ssl"></a>SSL로 디버거 연결 보안

기본적으로 ptvsd 원격 디버그 서버에 대한 연결은 암호로만 보호되고 모든 데이터는 일반 텍스트로 전달됩니다. 더 안전한 연결을 위해 ptvsd는 다음과 같이 설정하는 SSL을 지원합니다.

1. 원격 컴퓨터에서 다음과 같이 openssl을 사용하여 별도의 자체 서명된 인증서 및 키 파일을 생성합니다.
    
    ```bash
    openssl req -new -x509 -days 365 -nodes -out cert.cer -keyout cert.key
    ```

    openssl에서 메시지를 표시하면 **일반 이름**에 대해 호스트 이름 또는 IP 주소(어느 쪽이든 연결에 사용하는 항목)를 사용합니다.

    (자세한 내용은 Python `ssl` 모듈 문서의 [Self-signed certificates](http://docs.python.org/3/library/ssl.html#self-signed-certificates)(자체 서명된 인증서)를 참조하세요. 해당 문서의 명령은 결합된 단일 파일만 생성합니다.)

1. 코드에서 파일 이름을 값으로 사용하는 `certfile` 및 `keyfile` 인수를 포함하도록 `enable_attach`에 대한 호출을 수정합니다(이러한 인수는 표준 `ssl.wrap_socket` Python 함수에 대해 같은 의미를 지님).

    ```python
    ptvsd.enable_attach(secret='my_secret', certfile='cert.cer', keyfile='cert.key')
    ```
    
    로컬 컴퓨터의 코드 파일에서도 같은 변경 내용을 수행할 수 있지만, 이 코드는 실제로 실행되지 않으므로 절대적으로 불필요합니다.    

1. 원격 컴퓨터에서 Python 프로그램을 다시 시작하여 디버깅을 준비합니다.

1. Visual Studio가 설치된 Windows 컴퓨터에서 신뢰할 수 있는 루트 CA에 인증서를 추가하여 채널을 보호합니다.

    1. 원격 컴퓨터의 인증서 파일을 로컬 컴퓨터에 복사합니다.
    1. 제어판을 열고 **관리 도구 > 컴퓨터 인증서 관리**로 이동합니다.
    1. 나타나는 창의 왼쪽에서 **신뢰할 수 있는 루트 인증 기관**을 확장하고 **인증서**를 마우스 오른쪽 단추로 클릭한 다음 **모든 작업 > 가져오기...**를 선택합니다.
    1. 원격 컴퓨터에서 복사한 `.cer` 파일로 이동하여 이 파일을 선택한 다음 대화 상자를 클릭하여 가져오기를 완료합니다.

1. 앞에서 설명한 대로 Visual Studio에서 연결 프로세스를 반복하고 이제 **연결 대상**(또는 **한정자**)에 대한 프로토콜로 `tcps://`를 사용합니다.

    ![SSL로 원격 디버깅 전송 선택](~/python/media/remote-debugging-qualifier-ssl.png)

### <a name="warnings"></a>경고

아래에 설명한 대로 SSL을 통해 연결하면 Visual Studio에서 잠재적인 인증서 문제에 대한 메시지를 표시합니다. 경고를 무시하고 계속할 수 있지만, 채널이 여전히 도청으로부터 암호화되더라도 메시지 가로채기(man-in-the-middle) 공격에 개방될 수 있습니다.

1. 아래의 “원격 인증서를 신뢰할 수 없습니다.” 경고가 표시되는 경우 신뢰할 수 있는 루트 CA에 인증서를 제대로 추가하지 않았음을 의미합니다. 해당 단계를 확인하고 다시 시도합니다.

    ![SSL 인증서를 신뢰할 수 있습니다. 경고](~/python/media/remote-debugging-ssl-warning.png)

1. 아래의 “원격 인증서 이름이 호스트 이름과 일치하지 않습니다.” 경고가 표시되는 경우 인증서를 만들 때 **일반 이름**으로 올바른 호스트 이름 또는 IP 주소를 사용하지 않았음을 의미합니다.

    ![SSL 인증서 호스트 이름 경고](~/python/media/remote-debugging-ssl-warning2.png)

> [!Warning]
> 현재는 이러한 경고를 무시할 경우 Visual Studio 2017의 작동이 중단됩니다. 연결하기 전에 모든 문제를 해결해야 합니다.

