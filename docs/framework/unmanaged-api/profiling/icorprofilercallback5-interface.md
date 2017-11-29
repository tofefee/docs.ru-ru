---
title: "Интерфейс ICorProfilerCallback5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a862707dc64efbf3a9b1604a0e6a4ff1be81b43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="d81d7-102">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="d81d7-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="d81d7-103">Дополняет информацию, чтобы помочь профилировщику идентифицировать полное замыкание используемых объектов, при использовании либо [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) или [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)метод вместе с [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) и [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="d81d7-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="d81d7-104">Для подписки на уведомления, связанные с зависимыми дескрипторами профилировщик управляемой памяти должен реализовать `ICorProfilerCallback5`.</span><span class="sxs-lookup"><span data-stu-id="d81d7-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d81d7-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d81d7-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d81d7-106">Методы</span><span class="sxs-lookup"><span data-stu-id="d81d7-106">Methods</span></span>  
  
|<span data-ttu-id="d81d7-107">Метод</span><span class="sxs-lookup"><span data-stu-id="d81d7-107">Method</span></span>|<span data-ttu-id="d81d7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d81d7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d81d7-109">Метод ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="d81d7-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="d81d7-110">Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="d81d7-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d81d7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d81d7-111">Requirements</span></span>  
 <span data-ttu-id="d81d7-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d81d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d81d7-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d81d7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d81d7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81d7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d81d7-115">See Also</span></span>  
 [<span data-ttu-id="d81d7-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="d81d7-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="d81d7-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="d81d7-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)