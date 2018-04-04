2. F5 키를 누르면(또는 터미널 창에서 `vsce up`을 입력하면) 서비스가 실행됩니다. 이렇게 함으로써 새로 선택한 공간 `scott`에서 서비스를 자동으로 실행하게 됩니다. 
1. `vsce list`을 다시 실행하여 이를 확인할 수 있습니다. 첫째, `mywebapi`의 인스턴스가 `scott` 공간에서 실행되고 있음을 확인할 수 있습니다(`mainline`에서 실행되는 버전이 여전히 실행되고 있지만 표시되지는 않습니다). 둘째, `webfrontend`에 대한 액세스 포인트에는 텍스트 "scott-"이 접두사로 추가됩니다. 이 URL은 `scott` 공간에 고유하며 "scott URL"로 전송된 요청이 `scott` 공간의 서비스에 대한 첫 번째 경로를 시도하고 `mainline` 공간의 서비스로 돌아가게 된다는 것을 뜻합니다.

```
Name         Space     Chart              Ports   Updated     Access Points
-----------  --------  -----------------  ------  ----------  -------------
mywebapi     scott     mywebapi-0.1.0     80/TCP  15s ago     http://localhost:61466
webfrontend  mainline  webfrontend-0.1.0  80/TCP  5h ago      https://scott-webfrontend-contosodev.vsce.io
```

![](../media/space-routing.png)

연결된 환경의 이 기본 제공 기능을 사용하여 각 개발자가 자신의 공간에서 서비스의 전체 스택을 다시 만들도록 요구하지 않고도 공유 환경에서 코드를 종단 간 테스트할 수 있습니다. 이 가이트의 이전 단계에서 설명된 것처럼 이 라우팅은 앱 코드에서 전달된 전파 헤더를 요구합니다.

## <a name="test-code-in-a-space"></a>공간에서 코드 테스트
`webfrontend`와 연결해 `mywebapi`의 새 버전을 테스트하려면 webfrontend에 대한 공용 액세스 지점 URL에서 브라우저를 열고 정보 페이지로 이동합니다. 표시된 새 메시지를 확인해야 합니다.

이제 URL의 "scott-" 부분을 제거하고 브라우저를 새로 고칩니다. 이전 동작(`mainline`에서 실행 중인 `mywebapi` 버전으로 표시된)을 확인해야 합니다.