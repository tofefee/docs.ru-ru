---
title: "Метод ICLRAssemblyIdentityManager::IsStronglyNamed"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.IsStronglyNamed
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d0cb0bcaf5d19ec088511e64baffff9031911b32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="a1ccd-102">Метод ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="a1ccd-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="a1ccd-103">Возвращает значение, указывающее, является ли указанная сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ccd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1ccd-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1ccd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1ccd-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="a1ccd-106">[in] Непрозрачный канонические данные идентификации сборки должны быть оценены.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="a1ccd-107">[out] `true`, если ссылается на сборку `pwzAssemblyIdentity` параметр строго именованного; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1ccd-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a1ccd-108">Return Value</span></span>  
  
|<span data-ttu-id="a1ccd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1ccd-109">HRESULT</span></span>|<span data-ttu-id="a1ccd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a1ccd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1ccd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1ccd-111">S_OK</span></span>|<span data-ttu-id="a1ccd-112">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="a1ccd-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1ccd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1ccd-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1ccd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1ccd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1ccd-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-116">The call timed out.</span></span>|  
|<span data-ttu-id="a1ccd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1ccd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1ccd-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1ccd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1ccd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1ccd-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1ccd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1ccd-121">E_FAIL</span></span>|<span data-ttu-id="a1ccd-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1ccd-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1ccd-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1ccd-125">Требования</span><span class="sxs-lookup"><span data-stu-id="a1ccd-125">Requirements</span></span>  
 <span data-ttu-id="a1ccd-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ccd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ccd-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1ccd-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1ccd-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1ccd-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1ccd-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ccd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ccd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a1ccd-130">See Also</span></span>  
 [<span data-ttu-id="a1ccd-131">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a1ccd-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)