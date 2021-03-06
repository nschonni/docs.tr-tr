---
title: 'Nasıl yapılır: zaman eşzamanlılık özel durumlar belirtin'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 6890cc130f4f4101c02bb88c5f5666bcd5cf9b98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360826"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Nasıl yapılır: zaman eşzamanlılık özel durumlar belirtin
İçinde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Data.Linq.ChangeConflictException> nesneleri iyimser eşzamanlılık çakışmaları nedeniyle güncelleştirdiğinizde değil, özel durum. Daha fazla bilgi için bkz: [iyimser eşzamanlılık: genel bakış](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Değişiklikler veritabanına göndermeden önce eşzamanlılık özel durum olduğunda belirtebilirsiniz:  
  
-   İlk hata özel durum (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
-   Tüm güncelleştirme çalıştığında son, tüm hataları biriktirmesi ve özel durum birikmiş hataları rapor (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Oluştuğunda, <xref:System.Data.Linq.ChangeConflictException> özel durum erişim sağlayan bir <xref:System.Data.Linq.ChangeConflictCollection> koleksiyonu. Bu koleksiyon (bir tek başarısız güncelleştirme try eşlenen) her çakışma dahil olmak üzere ayrıntılarını sağlar <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> koleksiyonu. Tek bir üye olarak tutarlılık denetimi başarısız güncelleştirme her üye çakışma eşler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod iki değer örnekleri gösterir.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Değişiklik Çakışmalarını Yönetme](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Veri Değişiklikleri Yapma ve Gönderme](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
