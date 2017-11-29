---
title: "Метод ICorConfiguration::SetDebuggerThreadControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4716e814c352fceacd8b949c2670058cf8a03bf1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="b8dd8-102">Метод ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="b8dd8-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="b8dd8-103">Задает интерфейс обратного вызова, который будет вызываться службами отладки при блокировании и разблокировании потоков среды выполнения (CLR) общий язык для отладки.</span><span class="sxs-lookup"><span data-stu-id="b8dd8-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8dd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8dd8-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8dd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8dd8-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="b8dd8-106">[in] Указатель на [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) объект, который уведомляет основное приложение о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="b8dd8-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8dd8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b8dd8-107">Requirements</span></span>  
 <span data-ttu-id="b8dd8-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8dd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8dd8-109">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8dd8-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8dd8-110">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8dd8-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8dd8-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8dd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dd8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b8dd8-112">See Also</span></span>  
 [<span data-ttu-id="b8dd8-113">Icorconfiguration-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b8dd8-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)