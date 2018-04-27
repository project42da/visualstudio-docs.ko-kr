---
ms.topic: include
ms.openlocfilehash: 94e82185b05900101f91e4b368bb30d2aaceac03
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
## <a name="clean-up"></a>정리
연결된 환경 내에서 실행 중인 모든 서비스를 포함하여 Azure에서 연결된 환경을 완전히 삭제하려면 `vsce env rm` 명령을 사용합니다. 이 작업은 되돌릴 수 없다는 것을 명심하십시오.

다음 예제에서는 활성 Azure 구독에 연결된 환경을 나열한 다음, 리소스 그룹 'myenv-rg'에 있는 'myenv'라는 환경을 삭제합니다.

```cmd
vsce env list
vsce env rm --name myenv --resource-group myenv-rg
```

