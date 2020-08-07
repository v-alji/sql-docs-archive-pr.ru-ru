---
title: Метод StartService (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4d91646da2ac2c9f636655ff6c65808ba115e28f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733717"
---
# <a name="startservice-method-sqlservice-class"></a><span data-ttu-id="4a14a-102">Метод StartService (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="4a14a-102">StartService Method (SqlService Class)</span></span>
  <span data-ttu-id="4a14a-103">Пытается перевести службу в состояние запуска.</span><span class="sxs-lookup"><span data-stu-id="4a14a-103">Attempts to place the service into its started state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a14a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a14a-104">Syntax</span></span>  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4a14a-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="4a14a-105">Parts</span></span>  
 <span data-ttu-id="4a14a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4a14a-106">*object*</span></span>  
 <span data-ttu-id="4a14a-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="4a14a-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4a14a-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a14a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4a14a-109">Значение uint32 определяет одно из следующих состояний запуска.</span><span class="sxs-lookup"><span data-stu-id="4a14a-109">A uint32 value that specifies one of the following startup states.</span></span>  
  
 <span data-ttu-id="4a14a-110">0</span><span class="sxs-lookup"><span data-stu-id="4a14a-110">0</span></span>  
 <span data-ttu-id="4a14a-111">Успешно.</span><span class="sxs-lookup"><span data-stu-id="4a14a-111">Success.</span></span> <span data-ttu-id="4a14a-112">Запрос принят.</span><span class="sxs-lookup"><span data-stu-id="4a14a-112">The request was accepted.</span></span>  
  
 <span data-ttu-id="4a14a-113">1</span><span class="sxs-lookup"><span data-stu-id="4a14a-113">1</span></span>  
 <span data-ttu-id="4a14a-114">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4a14a-114">Not Supported.</span></span> <span data-ttu-id="4a14a-115">Запрос не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4a14a-115">The request is not supported.</span></span>  
  
 <span data-ttu-id="4a14a-116">2</span><span class="sxs-lookup"><span data-stu-id="4a14a-116">2</span></span>  
 <span data-ttu-id="4a14a-117">Доступ запрещен.</span><span class="sxs-lookup"><span data-stu-id="4a14a-117">Access Denied.</span></span> <span data-ttu-id="4a14a-118">Пользователь не имеет соответствующих прав доступа.</span><span class="sxs-lookup"><span data-stu-id="4a14a-118">The user did not have appropriate access.</span></span>  
  
 <span data-ttu-id="4a14a-119">3</span><span class="sxs-lookup"><span data-stu-id="4a14a-119">3</span></span>  
 <span data-ttu-id="4a14a-120">Запущены зависимые службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-120">Dependent Services Running.</span></span> <span data-ttu-id="4a14a-121">Службу нельзя остановить, так как от нее зависят другие работающие службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-121">The service cannot be stopped because other services that are running are dependent on it.</span></span>  
  
 <span data-ttu-id="4a14a-122">4</span><span class="sxs-lookup"><span data-stu-id="4a14a-122">4</span></span>  
 <span data-ttu-id="4a14a-123">Недопустимый управляющий код службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-123">Invalid Service Control.</span></span> <span data-ttu-id="4a14a-124">Запрошенный управляющий код недопустим или неприемлем для данной службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-124">The requested control code is not valid, or it is unacceptable to the service.</span></span>  
  
 <span data-ttu-id="4a14a-125">5</span><span class="sxs-lookup"><span data-stu-id="4a14a-125">5</span></span>  
 <span data-ttu-id="4a14a-126">Служба не принимает управляющий код.</span><span class="sxs-lookup"><span data-stu-id="4a14a-126">Service Cannot Accept Control.</span></span> <span data-ttu-id="4a14a-127">Запрошенный управляющий код не может быть отправлен службе, так как ее состояние (Win32_BaseService:State) равно 0, 1 или 2.</span><span class="sxs-lookup"><span data-stu-id="4a14a-127">The requested control code cannot be sent to the service because the state of the service (Win32_BaseService:State) is equal to 0, 1, or 2.</span></span>  
  
 <span data-ttu-id="4a14a-128">6</span><span class="sxs-lookup"><span data-stu-id="4a14a-128">6</span></span>  
 <span data-ttu-id="4a14a-129">Служба неактивна.</span><span class="sxs-lookup"><span data-stu-id="4a14a-129">Service Not Active.</span></span> <span data-ttu-id="4a14a-130">Служба не запущена.</span><span class="sxs-lookup"><span data-stu-id="4a14a-130">The service has not been started.</span></span>  
  
 <span data-ttu-id="4a14a-131">7</span><span class="sxs-lookup"><span data-stu-id="4a14a-131">7</span></span>  
 <span data-ttu-id="4a14a-132">Истекло время ожидания запроса службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-132">Service Request Timeout.</span></span> <span data-ttu-id="4a14a-133">Служба не ответила на запрос запуска за отведенное время.</span><span class="sxs-lookup"><span data-stu-id="4a14a-133">The service did not respond to the start request in a timely fashion.</span></span>  
  
 <span data-ttu-id="4a14a-134">8</span><span class="sxs-lookup"><span data-stu-id="4a14a-134">8</span></span>  
 <span data-ttu-id="4a14a-135">Неизвестный сбой.</span><span class="sxs-lookup"><span data-stu-id="4a14a-135">Unknown Failure.</span></span> <span data-ttu-id="4a14a-136">При запуске службы произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4a14a-136">An unknown failure occurred when starting the service.</span></span>  
  
 <span data-ttu-id="4a14a-137">9</span><span class="sxs-lookup"><span data-stu-id="4a14a-137">9</span></span>  
 <span data-ttu-id="4a14a-138">Путь не найден.</span><span class="sxs-lookup"><span data-stu-id="4a14a-138">Path Not Found.</span></span> <span data-ttu-id="4a14a-139">Не найден каталог исполняемого файла службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-139">The directory path to the service executable was not found.</span></span>  
  
 <span data-ttu-id="4a14a-140">10</span><span class="sxs-lookup"><span data-stu-id="4a14a-140">10</span></span>  
 <span data-ttu-id="4a14a-141">Служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="4a14a-141">Service Already Running.</span></span> <span data-ttu-id="4a14a-142">Служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="4a14a-142">The service is already running.</span></span>  
  
 <span data-ttu-id="4a14a-143">11</span><span class="sxs-lookup"><span data-stu-id="4a14a-143">11</span></span>  
 <span data-ttu-id="4a14a-144">База данных служб заблокирована.</span><span class="sxs-lookup"><span data-stu-id="4a14a-144">Service Database Locked.</span></span> <span data-ttu-id="4a14a-145">База данных для добавления новой службы заблокирована.</span><span class="sxs-lookup"><span data-stu-id="4a14a-145">The database to add a new service is locked.</span></span>  
  
 <span data-ttu-id="4a14a-146">12</span><span class="sxs-lookup"><span data-stu-id="4a14a-146">12</span></span>  
 <span data-ttu-id="4a14a-147">Удалена зависимость службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-147">Service Dependency Deleted.</span></span> <span data-ttu-id="4a14a-148">Служба, от которой зависит эта служба, была удалена из системы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-148">A dependency on which this service relies has been removed from the system.</span></span>  
  
 <span data-ttu-id="4a14a-149">13</span><span class="sxs-lookup"><span data-stu-id="4a14a-149">13</span></span>  
 <span data-ttu-id="4a14a-150">Сбой зависимости службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-150">Service Dependency Failure.</span></span> <span data-ttu-id="4a14a-151">Этой службе не удалось найти службу, которая необходима зависимой службе.</span><span class="sxs-lookup"><span data-stu-id="4a14a-151">The service failed to find the service needed from a dependent service.</span></span>  
  
 <span data-ttu-id="4a14a-152">14</span><span class="sxs-lookup"><span data-stu-id="4a14a-152">14</span></span>  
 <span data-ttu-id="4a14a-153">Служба отключена.</span><span class="sxs-lookup"><span data-stu-id="4a14a-153">Service Disabled.</span></span> <span data-ttu-id="4a14a-154">Эта служба была отключена в системе.</span><span class="sxs-lookup"><span data-stu-id="4a14a-154">The service has been disabled from the system.</span></span>  
  
 <span data-ttu-id="4a14a-155">15</span><span class="sxs-lookup"><span data-stu-id="4a14a-155">15</span></span>  
 <span data-ttu-id="4a14a-156">Сбой входа службы в систему.</span><span class="sxs-lookup"><span data-stu-id="4a14a-156">Service Logon Failed.</span></span> <span data-ttu-id="4a14a-157">Эта служба не поддерживает проверку подлинности, необходимую для работы в системе.</span><span class="sxs-lookup"><span data-stu-id="4a14a-157">The service does not have the correct authentication to run on the system.</span></span>  
  
 <span data-ttu-id="4a14a-158">16</span><span class="sxs-lookup"><span data-stu-id="4a14a-158">16</span></span>  
 <span data-ttu-id="4a14a-159">Служба помечена для удаления.</span><span class="sxs-lookup"><span data-stu-id="4a14a-159">Service Marked For Deletion.</span></span> <span data-ttu-id="4a14a-160">Служба удаляется из системы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-160">The service is being removed from the system.</span></span>  
  
 <span data-ttu-id="4a14a-161">17</span><span class="sxs-lookup"><span data-stu-id="4a14a-161">17</span></span>  
 <span data-ttu-id="4a14a-162">Служба без потоков.</span><span class="sxs-lookup"><span data-stu-id="4a14a-162">Service No Thread.</span></span> <span data-ttu-id="4a14a-163">Отсутствует поток исполнения для этой службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-163">There is no execution thread for the service.</span></span>  
  
 <span data-ttu-id="4a14a-164">18</span><span class="sxs-lookup"><span data-stu-id="4a14a-164">18</span></span>  
 <span data-ttu-id="4a14a-165">Состояние «Циклическая зависимость».</span><span class="sxs-lookup"><span data-stu-id="4a14a-165">Status Circular Dependency.</span></span> <span data-ttu-id="4a14a-166">При запуске службы обнаружены циклические зависимости.</span><span class="sxs-lookup"><span data-stu-id="4a14a-166">There are circular dependencies when starting the service.</span></span>  
  
 <span data-ttu-id="4a14a-167">19</span><span class="sxs-lookup"><span data-stu-id="4a14a-167">19</span></span>  
 <span data-ttu-id="4a14a-168">Состояние «Повторяющееся имя».</span><span class="sxs-lookup"><span data-stu-id="4a14a-168">Status Duplicate Name.</span></span> <span data-ttu-id="4a14a-169">Служба с таким именем уже запущена.</span><span class="sxs-lookup"><span data-stu-id="4a14a-169">There is a service running under the same name.</span></span>  
  
 <span data-ttu-id="4a14a-170">20</span><span class="sxs-lookup"><span data-stu-id="4a14a-170">20</span></span>  
 <span data-ttu-id="4a14a-171">Состояние «Недопустимое имя».</span><span class="sxs-lookup"><span data-stu-id="4a14a-171">Status Invalid Name.</span></span> <span data-ttu-id="4a14a-172">В имени службы присутствуют недопустимые символы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-172">There are characters that are not valid in the name of the service.</span></span>  
  
 <span data-ttu-id="4a14a-173">21</span><span class="sxs-lookup"><span data-stu-id="4a14a-173">21</span></span>  
 <span data-ttu-id="4a14a-174">Состояние «Недопустимый параметр».</span><span class="sxs-lookup"><span data-stu-id="4a14a-174">Status Invalid Parameter.</span></span> <span data-ttu-id="4a14a-175">Службе переданы недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="4a14a-175">Parameters that are not valid have been passed to the service.</span></span>  
  
 <span data-ttu-id="4a14a-176">22</span><span class="sxs-lookup"><span data-stu-id="4a14a-176">22</span></span>  
 <span data-ttu-id="4a14a-177">Состояние «Недействительная учетная запись службы».</span><span class="sxs-lookup"><span data-stu-id="4a14a-177">Status Invalid Service Account.</span></span> <span data-ttu-id="4a14a-178">Учетная запись, под именем которой должна выполняться служба, неверна или не обладает разрешениями для запуска этой службы.</span><span class="sxs-lookup"><span data-stu-id="4a14a-178">The account which this service is to run under is not valid, or it lacks the permissions to run the service.</span></span>  
  
 <span data-ttu-id="4a14a-179">23</span><span class="sxs-lookup"><span data-stu-id="4a14a-179">23</span></span>  
 <span data-ttu-id="4a14a-180">Состояние «Служба существует».</span><span class="sxs-lookup"><span data-stu-id="4a14a-180">Status Service Exists.</span></span> <span data-ttu-id="4a14a-181">Служба существует в базе данных доступных в системе служб.</span><span class="sxs-lookup"><span data-stu-id="4a14a-181">The service exists in the database of services available from the system.</span></span>  
  
 <span data-ttu-id="4a14a-182">24</span><span class="sxs-lookup"><span data-stu-id="4a14a-182">24</span></span>  
 <span data-ttu-id="4a14a-183">Служба уже приостановлена.</span><span class="sxs-lookup"><span data-stu-id="4a14a-183">Service Already Paused.</span></span> <span data-ttu-id="4a14a-184">Служба в данный момент приостановлена в системе.</span><span class="sxs-lookup"><span data-stu-id="4a14a-184">The service is currently paused in the system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a14a-185">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a14a-185">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a14a-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a14a-186">See Also</span></span>  
 <span data-ttu-id="4a14a-187">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4a14a-187">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
