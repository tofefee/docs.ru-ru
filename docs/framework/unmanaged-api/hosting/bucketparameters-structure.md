---
title: Структура BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b5e4db8e385baefe3067755bbdc4555c5887ab6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429959"
---
# <a name="bucketparameters-structure"></a>Структура BucketParameters
Хранит имя типа события и параметры для текущего исключения, связанного с событием.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`fInited`|`true`, если остальная часть этой структуры является допустимым; в противном случае `false`.|  
|`pszEventTypeName`|Имя типа события.|  
|`pszParams`|Массив строк, каждая из которых задает параметр для текущего исключения, связанного с событием.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
