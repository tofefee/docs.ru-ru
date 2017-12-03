---
title: "Функция CreateAssemblyCache"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyCache
helpviewer_keywords: CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b6dfc8cd90b5a37b82b26d4f8e494159dc1fd30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblycache-function"></a><span data-ttu-id="73925-102">Функция CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="73925-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="73925-103">Возвращает указатель на новый [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) экземпляр, представляющий глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="73925-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73925-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73925-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73925-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73925-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="73925-106">[out] Возвращенный `IAssemblyCache` указателя.</span><span class="sxs-lookup"><span data-stu-id="73925-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="73925-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="73925-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="73925-108">`dwReserved`должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="73925-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73925-109">Требования</span><span class="sxs-lookup"><span data-stu-id="73925-109">Requirements</span></span>  
 <span data-ttu-id="73925-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73925-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73925-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="73925-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="73925-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73925-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73925-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73925-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73925-114">См. также</span><span class="sxs-lookup"><span data-stu-id="73925-114">See Also</span></span>  
 [<span data-ttu-id="73925-115">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="73925-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="73925-116">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="73925-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="73925-117">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="73925-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)