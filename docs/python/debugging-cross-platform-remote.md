---
title: "Visual Studio용 Python 도구로 플랫폼 간 원격 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
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
translationtype: Human Translation
ms.sourcegitcommit: 7d726441c2d6953bd7b50451bec7fff05d5d71b0
ms.openlocfilehash: 7634da4bdc2b0186f410acb4eaf57a70ddea3e91
ms.lasthandoff: 03/10/2017

---

# <a name="remotely-debugging-python-code"></a>Python 코드 원격 디버깅

PTVS(Visual Studio용 Python 도구)는 Windows 컴퓨터에서 Python 응용 프로그램을 로컬 및 원격으로 실행하고 디버그할 수 있습니다([원격 디버깅](../debugger/remote-debugging.md) 참조). 또한 [ptvsd 라이브러리](https://pypi.python.org/pypi/ptvsd)를 사용하여 CPython 이외의 다른 운영 체제, 장치 또는 Python 구현에서 원격으로 디버그할 수도 있습니다.

ptvsd를 사용하는 경우 디버그되는 Python 코드는 Visual Studio에서 연결할 수 있는 디버그 서버를 호스팅합니다. 이렇게 하려면 서버를 가져오고 사용할 수 있도록 코드를 약간 수정해야 하며, TCP 연결을 허용하기 위해 원격 컴퓨터에 네트워크 또는 방화벽 구성이 필요할 수 있습니다.

원격 디버깅에 대한 소개는 [자세히 알아보기: 플랫폼 간 원격 디버깅](https://youtu.be/y1Qq7BrV6Cc)(youtube.com, 6분 22초)을 참조하세요.

> [!VIDEO https://www.youtube.com/embed/y1Qq7BrV6Cc]

## <a name="preparing-the-script-for-debugging"></a>디버그할 스크립트 준비

1. 원격 컴퓨터에 다음 코드를 사용하여 Python 파일을 만듭니다.

  ```python
  import random

  guesses_made = 0
  name = raw_input('Hello! What is your name?\n')
  number = random.randint(1, 20)
  print 'Well, {0}, I am thinking of a number between 1 and 20.'.format(name)

  while guesses_made < 6:
      guess = int(raw_input('Take a guess: '))
      guesses_made += 1
      if guess < number:
          print 'Your guess is too low.'
      if guess > number:
          print 'Your guess is too high.'
      if guess == number:
          break
  if guess == number:
      print 'Good job, {0}! You guessed my number in {1} guesses!'.format(name, guesses_made)
  else:
      print 'Nope. The number I was thinking of was {0}'.format(number)
  ```
 
1. `pip install ptvsd`를 사용하여 사용자 환경에 `ptvsd` 패키지를 설치합니다.

1. 스크립트에서 가능한 가장 빠른 지점에 다른 코드보다 먼저 해당 코드를 추가하여 원격 디버깅을 사용하도록 설정합니다. (엄격한 요구 사항은 아니지만, `enable_attach` 함수를 호출하기 전에 생성된 모든 백그라운드 스레드를 디버그할 수는 없습니다.)

   ```python
   import ptvsd
   ptvsd.enable_attach(secret='my_secret')
   ```

   `enable_attach`에 전달된 `secret` 매개 변수는 실행 중인 스크립트에 대한 액세스를 제한하는 데 사용됩니다. 연결할 때 Visual Studio에서 이 매개 변수를 지정해야 합니다. 그렇지 않으면 연결이 거부됩니다. 이 기능을 사용하지 않고 다른 사용자가 연결할 수 있게 하려면 `enable_attach(secret=None)`을 사용합니다.

1. 원격 컴퓨터에서 파일을 저장하고 스크립트를 시작합니다. `enable_attach`에 대한 호출이 백그라운드에서 실행되고 들어오는 연결을 기다립니다. 원하는 경우 디버거가 연결될 때까지 `enable_attach` 뒤에 `wait_for_attach` 함수를 호출하여 프로그램을 차단할 수 있습니다.

`enable_attach` 및 `wait_for_attach` 외에도, ptvsd는 디버거가 연결되어 있으면 중단점을 프로그래밍 방식으로 작동하는 `break_into_debugger` 도우미 함수를 제공합니다. 또한 디버거가 연결되어 있으면 `True`를 반환하는 `is_attached` 함수도 있지만, 다른 `ptvsd` 함수를 호출하기 전에 이 결과를 확인할 필요가 없습니다.

## <a name="attaching-remotely-from-python-tools"></a>Python 도구에서 원격으로 연결

이 단계에서는 간단한 중단점을 설정하여 원격 프로세스를 중지합니다.

1. 로컬 컴퓨터에 원격 파일의 복사본을 만들고 Visual Studio에서 엽니다. 파일의 위치는 중요하지 않지만, 이름은 연결될 원격 컴퓨터의 스크립트 이름과 일치해야 합니다.

1. **디버그 > 프로세스에 연결**을 선택하여 [프로세스에 연결] 대화 상자를 엽니다.

1. **전송**을 **Python 원격 디버깅**으로 설정합니다.

1. **한정자** 필드에 원격 컴퓨터의 주소를 입력하고 Enter 키를 누릅니다. 이 경우 해당 컴퓨터에서 사용 가능한 프로세스가 나열되어야 합니다.

![한정자 입력 및 프로세스 나열](media/remote-debugging-qualifier.png)

1. 이 단계에서의 오류는 일반적으로 비밀이 일치하지 않거나, `ptvsd` 버전이 PTVS에서 사용되는 것과 일치하지 않거나, 연결을 설정할 수 없다는 것을 나타냅니다. 연결할 수 없는 일반적 원인 중 하나는 열린 디버그 서버 포트(기본값: 5678)를 차단하는 방화벽이 원격 컴퓨터에 있다는 것입니다. 방화벽을 다시 구성하거나 다른 포트를 사용할 수 있습니다. 후자는 다음과 같이 `address` 매개 변수에서 `enable_attach`에 대한 호출에서 해당 포트를 명시적으로 지정하여 수행할 수 있습니다.

  ```python
  ptvsd.enable_attach(secret = 'my_secret', address = ('0.0.0.0', 8080))
  ```

  주소 형식은 표준 Python 모듈 소켓에서 `AF_INET` 형식의 소켓에 대해 사용하는 것과 동일합니다. 자세한 내용은 [ 설명서 ](http://docs.python.org/3/library/socket.html#socket-families)를 참조하세요. 

1. 프로세스가 목록에 표시되면 해당 프로세스를 두 번 클릭하여 연결합니다. 스크립트가 계속 실행되는 동안 Visual Studio에서 디버깅 도구를 표시합니다. 위에서 보여 주는 예제 스크립트의 경우 숫자를 입력하면 적중될 중단점이 발생합니다.

    ![적중된 중단점](media/remote-debugging-breakpoint-hit.png)

1. 이 시점에서 일반적인 PTVS 디버깅 기능은 모두 사용할 수 있습니다. 

1. 디버깅을 중지하면 Visual Studio가 스크립트에서 분리되지만, 해당 스크립트는 원격 컴퓨터에서 계속 실행됩니다. 또한 디버그 서버가 백그라운드 스레드에서 계속 실행되므로 나중에 동일한 절차를 사용하여 해당 프로세스에 다시 연결할 수도 있습니다.


## <a name="securing-the-debugger-connection-with-ssl"></a>SSL로 디버거 연결 보안

기본적으로 PTVS 원격 디버그 서버에 대한 연결은 어떤 방법으로도 보호되지 않습니다. 비밀을 가지고 있는 사용자는 모두 연결할 수 있으며, 모든 데이터가 일반 텍스트로 전달됩니다. 따라서 네트워크의 다른 사용자가 데이터에서 스누핑하거나 MITM(메시지 가로채기(man-in-the-middle)) 공격도 실행할 수 있습니다. 보호되지 않은 네트워크 또는 인터넷을 통해 디버그할 때 이를 방지하기 위해 디버그 서버에서 SSL을 지원합니다. 

SSL로 채널을 보호하려면 SSL 인증서가 필요합니다. [Python 표준 모듈(`ssl`)에 대한 설명서](http://docs.python.org/3/library/ssl.html#self-signed-certificates)(영문)에서 설명한 대로 자체 서명된 인증서를 직접 생성할 수 있습니다. MITM 공격을 방지하려면 PTVS를 실행하는 Windows 컴퓨터의 CA 루트 저장소에 이와 같이 생성된 인증서를 추가해야 합니다. 이렇게 하려면 [인증서 및/또는 개인 키를 내보내는 방법](https://answers.microsoft.com/en-us/windows/forum/windows_10-security/how-do-i-export-certificates-andor-private-keys/7722900a-e848-4076-bc50-9e2f5e3c66ac)(영문)에서 설명한 대로 인증서 관리자(certmgr.msc)를 사용하여 수행할 수 있습니다. 가져올 별도의 인증서 파일(개인 키와 결합된 단일 파일이 아님)이 있어야 합니다. 

인증서와 개인 키 파일을 생성하고 등록한 후에는 스크립트에서 `enable_attach`에 대한 호출을 업데이트하여 사용해야 합니다. 이는 `ssl.wrap_socket` 표준 Python 함수와 같은 의미를 갖는 `certfile` 및 `keyfile` 매개 변수를 통해 수행됩니다. 예를 들어 인증서 파일과 키 파일의 이름이 각각 `my_cert.cer` 및 `my_cert.key`인 경우 다음을 사용합니다. 

```python
ptvsd.enable_attach(secret='my_secret', certfile='my_cert.cer', keyfile='my_cert.key')
```

연결 프로세스는 한정자에서 `tcp://` 체계를 사용하는 대신 `tcps://`를 사용한다는 점을 제외하고는 앞에서 설명한 것과 똑같습니다. 

![SSL로 원격 디버깅 전송 선택](media/remote-debugging-qualifier-ssl.png)

CA 루트 저장소에 인증서를 추가하지 않은 경우 다음과 같은 경고 메시지가 표시됩니다. 

![SSL 인증서 경고](media/remote-debugging-ssl-warning.png)

이 경고를 무시하고 디버깅을 진행하도록 선택할 수 있습니다. 채널은 도청에 대비하여 여전히 암호화되지만, 경고를 무시하면 MITM 공격에 노출될 가능성이 높아집니다.

