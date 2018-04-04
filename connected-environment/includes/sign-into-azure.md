## <a name="sign-in-to-azure"></a>Azure에 로그인
개발 환경을 만들려면 Azure에 로그인해야 합니다. 터미널 창에서 다음 명령을 입력합니다.
```cmd
az login
```

> [!Note]
> Azure 구독이 없는 경우 [무료 계정](https://azure.microsoft.com/free)을 만들 수 있습니다.

### <a name="if-you-have-multiple-azure-subscriptions"></a>여러 Azure 구독이 있는 경우...
다음을 실행하여 구독을 볼 수 있습니다. 
```cmd
az account list
```
JSON 출력에서 `isDefault: true`이 있는 구독을 찾습니다.
사용하려는 구독이 없는 경우 기본 구독을 변경할 수 있습니다.
```cmd
az account set --subscription <subscription ID>
```
