---
title: ICLRGCManager2::SetGCStartupLimitsEx Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65fbf0bf42f7312ad80b61bf452b62a4d0ff93c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436130"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a>ICLRGCManager2::SetGCStartupLimitsEx Yöntemi
Çöp toplama kesim boyutunu ve en büyük boyutu 0 atık toplama sistemin nesil ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `SegmentSize`  
 [in] Çöp toplama kesim belirtilen boyutu.  
  
 Minimum kesim boyutu 4 MB'tır. Kesimleri artan aralıklarla 1 MB veya daha büyük olabilir.  
  
 `MaxGen0Size`  
 [in] 0 oluşturma için belirtilen en büyük boyutu.  
  
 Minimum kuşak 0 boyutu 64 KB'tır.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimitsEx` başarıyla döndürüldü.|  
|HOST_E_CLRNOTAVAILABLE|Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan kilidi kendisine ait değil.|  
|HOST_E_ABANDONED|Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.|  
|E_FAIL|Bilinmeyen yıkıcı bir hata oluştu. CLR, artık bir yöntem E_FAIL döndükten sonra işlemi içinde kullanılamaz. Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Değerleri, `SetGCStartupLimitsEx` kümeleri yalnızca ana başlatılmadan önce belirtilebilir. Daha sonra çağrılar `SetGCStartupLimitsEx` göz ardı edilir.  
  
 Her iki parametre diğer etkilemeden ayarlamak için değiştirmek istemiyorsanız parametresi için 0 (sıfır) belirtin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomatik Bellek Yönetimi](../../../../docs/standard/automatic-memory-management.md)  
 [Atık Toplama](../../../../docs/standard/garbage-collection/index.md)  
 [ICLRControl Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRGCManager2 Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
