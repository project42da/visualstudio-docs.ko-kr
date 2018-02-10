---
title: "이벤트 처리기에 모델 외부의 변경 내용을 전파 하기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, programming domain models
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8b5c957fbc3ae5eb3e71f087c57cbf07188de2ff
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="event-handlers-propagate-changes-outside-the-model"></a>이벤트 처리기로 모델 외부의 변경 내용 전파
Visualization and Modeling SDK에서와 같은 비 저장소 변수, 파일, 다른 저장소 또는 다른 모델 저장소의 외부 리소스에 대 한 변경 내용을 전파 하는 저장소 이벤트 처리기를 정의할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장 합니다. 이벤트 처리기를 트리거하는 이벤트가 발생 한 트랜잭션의 끝 다음에 실행을 저장 합니다. 또한 실행 취소 또는 다시 실행 작업에서 실행 됩니다. 따라서 저장소 규칙과 달리 저장소 이벤트는 외부 저장소에 있는 값을 업데이트 하는 데 가장 유용 합니다. 저장소 이벤트 처리기는 클래스를 수신 하도록 등록 된.NET 이벤트와 달리: 각 인스턴스에 대해 별도 처리기를 등록할 필요가 없습니다. 변경 처리를 위해 다양 한 방법 중 하나를 선택 하는 방법에 대 한 자세한 내용은 참조 [에 대응 하 고 변경 내용을 전파](../modeling/responding-to-and-propagating-changes.md)합니다.  
  
 그래픽 화면 및 기타 사용자 인터페이스 컨트롤은 저장소 이벤트에서 처리 될 수 있는 외부 리소스의 예입니다.  
  
### <a name="to-define-a-store-event"></a>저장소 이벤트 정의 하려면  
  
1.  모니터링 하려는 이벤트의 유형을 선택 합니다. 속성의 전체 목록을 확인 <xref:Microsoft.VisualStudio.Modeling.EventManagerDirectory>합니다. 각 속성은 이벤트의 형식에 해당 합니다. 가장 자주 사용 하는 이벤트 유형은:  
  
    -   `ElementAdded`-트리거될 때 모델 요소 링크 관계, 셰이프 또는 연결선 생성 됩니다.  
  
    -   ElementPropertyChanged-트리거되는 경우의 값을 `Normal` 도메인 속성을 변경 합니다. 이 이벤트는 신규 버전과 기존 값이 같지 않은지 하는 경우에 트리거됩니다. 이 이벤트는 계산 및 사용자 지정 저장소 속성에 적용할 수 없습니다.  
  
         관계 링크에 해당 하는 역할 속성에 적용할 수 없습니다. 대신를 사용 하 여 `ElementAdded` 도메인 관계를 모니터링할 수 있습니다.  
  
    -   `ElementDeleted`-모델 요소 뒤 트리거된 관계, 셰이프 또는 연결선 삭제 되었습니다. 속성 값은 요소의 계속 액세스할 수 있습니다 하지만 다른 요소에 관계가 없음을 의미 합니다.  
  
2.  Partial 클래스 정의 대 한 추가 *YourDsl * * * DocData** 별도 코드 파일에 **DslPackage** 프로젝트.  
  
3.  다음 예제와 같이 메서드로 이벤트의 코드를 작성 합니다. 것이 `static`액세스 하려는 경우가 아니면 `DocData`합니다.  
  
4.  재정의 `OnDocumentLoaded()` 처리기를 등록 합니다. 둘 이상의 처리기를 설정한 경우에 같은 곳에서 등록할 수 있습니다.  
  
 등록 코드의 위치는 중요 하지 않습니다. `DocView.LoadView()`대체 위치가입니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.VisualStudio.Modeling;  
  
namespace Company.MusicLib  
{  
  partial class MusicLibDocData  
  {  
    // Register store events here or in DocView.LoadView().  
    protected override void OnDocumentLoaded()  
    {  
      base.OnDocumentLoaded(); // Don't forget this.  
  
      #region Store event handler registration.       
      Store store = this.Store;  
      EventManagerDirectory emd = store.EventManagerDirectory;  
      DomainRelationshipInfo linkInfo = store.DomainDataDirectory  
          .FindDomainRelationship(typeof(ArtistAppearsInAlbum));  
      emd.ElementAdded.Add(linkInfo,   
          new EventHandler<ElementAddedEventArgs>(AddLink));  
      emd.ElementDeleted.Add(linkInfo,   
          new EventHandler<ElementDeletedEventArgs>(RemoveLink));  
  
      #endregion Store event handlers.  
    }  
  
    private void AddLink(object sender, ElementAddedEventArgs e)  
    {  
      ArtistAppearsInAlbum link = e.ModelElement as ArtistAppearsInAlbum;  
      if (link != null)   
            ExternalDatabase.Add(link.Artist.Name, link.Album.Title);  
    }  
    private void RemoveLink(object sender, ElementDeletedEventArgs e)  
    {  
      ArtistAppearsInAlbum link = e.ModelElement as ArtistAppearsInAlbum;  
      if (link != null)   
            ExternalDatabase.Delete(link.Artist.Name, link.Album.Title);  
    }  
  }  
  
}  
  
```  
  
## <a name="using-events-to-make-undoable-adjustments-in-the-store"></a>이벤트를 사용 하 여 저장소에 대 한 실행 취소할 수 있는 조정 하려면  
 저장소 이벤트 사용 되지 않습니다 일반적으로 저장소를 내 변경 내용 전파에 대 한 이벤트 처리기는 트랜잭션이 커밋된 후 실행 되기 때문에. 대신, 저장소 규칙을 사용 합니다. 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
 그러나 사용자가을 원래 이벤트에서 별도로 추가 업데이트를 취소할 수를 저장소에 추가 업데이트를 확인 하는 이벤트 처리기를 사용할 수 있습니다. 예를 들어, 소문자 문자는 앨범 제목에 대 한 일반적인 규칙입니다. 사용자가 입력 한 것 대문자로 후 소문자로 제목 수정 하는 저장소 이벤트 처리기를 작성할 수 있습니다. 하지만 사용자 대문자 문자 복원 수정 내용을 취소 하려면 실행 취소 명령을 사용할 수 없습니다. 두 번째 실행 취소 사용자의 변경 내용을 삭제 합니다.  
  
 반면, 동일한 작업을 수행 하는 저장소 규칙 작성 된 경우 사용자의 변경 내용을 하 수정 내용을 것은 같은 트랜잭션에 있는 하는 사용자는 원래 변경 그대로 유지 하면서를 조정 하면 취소할 수 없습니다.  
  
```  
  
partial class MusicLibDocView  
{  
    // Register store events here or in DocData.OnDocumentLoaded().  
    protected override void LoadView()  
    {  
      /* Register store event handler for Album Title property. */  
      // Get reflection data for property:  
      DomainPropertyInfo propertyInfo =   
        this.DocData.Store.DomainDataDirectory  
        .FindDomainProperty(Album.TitleDomainPropertyId);  
      // Add to property handler list:  
      this.DocData.Store.EventManagerDirectory  
        .ElementPropertyChanged.Add(propertyInfo,  
        new EventHandler<ElementPropertyChangedEventArgs>  
             (AlbumTitleAdjuster));  
  
      /*  
      // Alternatively, you can set one handler for   
      // all properties of a class.  
      // Your handler has to determine which property changed.  
      DomainClassInfo classInfo = this.Store.DomainDataDirectory  
           .FindDomainClass(typeof(Album));  
      this.Store.EventManagerDirectory  
          .ElementPropertyChanged.Add(classInfo,  
        new EventHandler<ElementPropertyChangedEventArgs>  
             (AlbumTitleAdjuster));  
       */  
      return base.LoadView();  
    }  
  
// Undoable adjustment after a property is changed.   
// Method can be static since no local access.  
private static void AlbumTitleAdjuster(object sender,  
         ElementPropertyChangedEventArgs e)  
{  
  Album album = e.ModelElement as Album;  
  Store store = album.Store;  
  
  // We mustn't update the store in an Undo:  
  if (store.InUndoRedoOrRollback   
      || store.InSerializationTransaction)  
      return;  
  
  if (e.DomainProperty.Id == Album.TitleDomainPropertyId)  
  {  
    string newValue = (string)e.NewValue;  
    string lowerCase = newValue.ToLowerInvariant();  
    if (!newValue.Equals(lowerCase))  
    {  
      using (Transaction t = store.TransactionManager  
            .BeginTransaction("adjust album title"))  
      {  
        album.Title = lowerCase;  
        t.Commit();  
      } // Beware! This could trigger the event again.  
    }  
  }  
  // else other properties of this class.  
}  
  
```  
  
 저장소를 업데이트 하는 이벤트 작성 하는 경우:  
  
-   사용 하 여 `store.InUndoRedoOrRollback` 되지 않도록 하기 위해 변경 내용을 실행 취소의 모델 요소에 있습니다. 트랜잭션 관리자를 다시 원래 상태로 저장소에 모든를 설정 합니다.  
  
-   사용 하 여 `store.InSerializationTransaction` 에 모델 파일에서 로드 되는 동안 변경 하지 마십시오.  
  
-   변경 내용을 추가로를 트리거할 이벤트를 발생 합니다. 무한 루프를 방지 하 고 있는지 확인 합니다.  
  
## <a name="store-event-types"></a>이벤트 유형 저장  
 이벤트 유형별로 Store.EventManagerDirectory에서 컬렉션에 해당합니다. 추가 하거나 언제 든 지 이벤트 처리기를 제거할 수 있습니다 하지만 문서를 로드 하는 경우 추가 별로있지 않습니다.  
  
|`EventManagerDirectory`속성 이름|실행할 때 실행|  
|-------------------------------------------|-------------------|  
|ElementAdded|도메인 클래스, 도메인 관계, 도형, 커넥터 또는 다이어그램의 인스턴스가 생성 됩니다.|  
|ElementDeleted|모델 요소 상점의 요소 디렉터리에서 제거 되었습니다 며 더 이상 소스 또는 모든 관계의 대상입니다. 요소는 메모리에서 실제로 삭제 되지 않습니다 되지만 이후 실행 취소의 경우 유지 됩니다.|  
|ElementEventsBegun|외부 트랜잭션이 끝날 때 호출 됩니다.|  
|ElementEventsEnded|기타 모든 이벤트가 처리 될 때 호출 됩니다.|  
|ElementMoved|다른 모델 요소 하나의 저장소 파티션에서 이동 되었습니다.<br /><br /> 다이어그램에서 모양의 위치에는 관련 되지 않았습니다.|  
|ElementPropertyChanged|도메인 속성의 값이 변경 되었습니다. 이 이전 구문과 새 값이 같지 않은지 하는 경우에 실행 됩니다.|  
|RolePlayerChanged|관계의 두 가지 역할 (종단) 중 하나에 새 요소를 참조합니다.|  
|RolePlayerOrderChanged|1 보다 큰 복합성 역할에서는 링크 순서 변경 되었습니다.|  
|TransactionBeginning||  
|TransactionCommitted||  
|TransactionRolledBack||  
  
## <a name="see-also"></a>참고 항목  
 [응답 하 고 변경 내용 전파](../modeling/responding-to-and-propagating-changes.md)   
 [샘플 코드: 회로 다이어그램](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
