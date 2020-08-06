---
title: Параметр конфигурации сервера "clr enabled" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b83cd0e00bdd32c8b44667209544c8e81b1e90c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655364"
---
# <a name="clr-enabled-server-configuration-option"></a><span data-ttu-id="6c460-102">Параметр конфигурации сервера «clr enabled»</span><span class="sxs-lookup"><span data-stu-id="6c460-102">clr enabled Server Configuration Option</span></span>
  <span data-ttu-id="6c460-103">Используйте параметр «clr enabled», чтобы указать, может ли [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]выполнять пользовательские сборки.</span><span class="sxs-lookup"><span data-stu-id="6c460-103">Use the clr enabled option to specify whether user assemblies can be run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6c460-104">Параметр clr enabled предлагает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="6c460-104">The clr enabled option provides the following values.</span></span>  
  
|<span data-ttu-id="6c460-105">Значение</span><span class="sxs-lookup"><span data-stu-id="6c460-105">Value</span></span>|<span data-ttu-id="6c460-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6c460-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c460-107">0</span><span class="sxs-lookup"><span data-stu-id="6c460-107">0</span></span>|<span data-ttu-id="6c460-108">Выполнение сборок не разрешается в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c460-108">Assembly execution not allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="6c460-109">1</span><span class="sxs-lookup"><span data-stu-id="6c460-109">1</span></span>|<span data-ttu-id="6c460-110">Выполнение сборок разрешается в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c460-110">Assembly execution allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
 <span data-ttu-id="6c460-111">Чтобы изменения этого параметра вступили в силу, необходимо перезагрузить серверы WOW64.</span><span class="sxs-lookup"><span data-stu-id="6c460-111">WOW64 servers must be restarted before the changes to this setting will take effect.</span></span> <span data-ttu-id="6c460-112">Для других типов серверов перезагрузка необязательна.</span><span class="sxs-lookup"><span data-stu-id="6c460-112">Restart is not required for other server types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c460-113">При выполнении инструкции RECONFIGURE и изменении значения параметра «clr enabled» с 1 на 0 все домены приложений, содержащих пользовательские сборки, немедленно выгружаются.</span><span class="sxs-lookup"><span data-stu-id="6c460-113">When RECONFIGURE is run and the run value of the clr enabled option is changed from 1 to 0, all application domains containing user assemblies are immediately unloaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c460-114">Выполнение в среде CLR не поддерживается при использовании упрощенных пулов.</span><span class="sxs-lookup"><span data-stu-id="6c460-114">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="6c460-115">Отключите один из двух параметров: clr enabled или lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="6c460-115">Disable one of two options: "clr enabled" or "lightweight pooling.</span></span> <span data-ttu-id="6c460-116">Функции, зависящие от среды CLR и неправильно работающие в режиме волокон, включают тип данных `hierarchy`, репликацию и управление на основе политик.</span><span class="sxs-lookup"><span data-stu-id="6c460-116">Features that rely upon CLR and that do not work properly in fiber mode include the `hierarchy` data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c460-117">Пример</span><span class="sxs-lookup"><span data-stu-id="6c460-117">Example</span></span>  
 <span data-ttu-id="6c460-118">В следующем примере сначала отображается текущая настройка параметра clr enabled, а затем параметр включается с заданием значения 1.</span><span class="sxs-lookup"><span data-stu-id="6c460-118">The following example first displays the current setting of the clr enabled option and then enables the option by setting the option value to 1.</span></span> <span data-ttu-id="6c460-119">Чтобы отключить этот параметр, задайте значение 0.</span><span class="sxs-lookup"><span data-stu-id="6c460-119">To disable the option, set the value to 0.</span></span>  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c460-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c460-120">See Also</span></span>  
 <span data-ttu-id="6c460-121">[Параметр конфигурации сервера «использование упрощенных пулов»](lightweight-pooling-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="6c460-121">[lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md) </span></span>  
 <span data-ttu-id="6c460-122">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c460-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="6c460-123">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c460-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="6c460-124">Параметр конфигурации сервера «использование упрощенных пулов»</span><span class="sxs-lookup"><span data-stu-id="6c460-124">lightweight pooling Server Configuration Option</span></span>](lightweight-pooling-server-configuration-option.md)  
  
  
