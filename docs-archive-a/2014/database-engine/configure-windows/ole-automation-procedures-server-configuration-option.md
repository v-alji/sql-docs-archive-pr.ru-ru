---
title: Параметр конфигурации сервера "Ole Automation Procedures" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d34615ce1f808c1015c9c3d312a38a67dba291b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728682"
---
# <a name="ole-automation-procedures-server-configuration-option"></a><span data-ttu-id="9069e-102">Параметр конфигурации сервера «Ole Automation Procedures»</span><span class="sxs-lookup"><span data-stu-id="9069e-102">Ole Automation Procedures Server Configuration Option</span></span>
  <span data-ttu-id="9069e-103">C помощью параметра `Ole Automation Procedures` можно указать возможность создания экземпляров объектов OLE-автоматизации в пакетах [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9069e-103">Use the `Ole Automation Procedures` option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches.</span></span> <span data-ttu-id="9069e-104">Этот параметр также можно настроить с помощью управления на основе политики или с помощью хранимой процедуры **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="9069e-104">This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure.</span></span> <span data-ttu-id="9069e-105">Дополнительные сведения см. в разделе [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="9069e-105">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
 <span data-ttu-id="9069e-106">Параметр `Ole Automation Procedures` может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9069e-106">The `Ole Automation Procedures` option can be set to the following values.</span></span>  
  
 <span data-ttu-id="9069e-107">0</span><span class="sxs-lookup"><span data-stu-id="9069e-107">0</span></span>  
 <span data-ttu-id="9069e-108">Процедуры OLE-автоматизации отключены.</span><span class="sxs-lookup"><span data-stu-id="9069e-108">OLE Automation Procedures are disabled.</span></span> <span data-ttu-id="9069e-109">По умолчанию для новых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9069e-109">Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9069e-110">1</span><span class="sxs-lookup"><span data-stu-id="9069e-110">1</span></span>  
 <span data-ttu-id="9069e-111">Процедуры OLE-автоматизации включены.</span><span class="sxs-lookup"><span data-stu-id="9069e-111">OLE Automation Procedures are enabled.</span></span>  
  
 <span data-ttu-id="9069e-112">После включения процедур OLE-автоматизации процедура **sp_OACreate** запустит общую среду выполнения OLE.</span><span class="sxs-lookup"><span data-stu-id="9069e-112">When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.</span></span>  
  
 <span data-ttu-id="9069e-113">Текущее значение `Ole Automation Procedures` параметра можно просмотреть и изменить с помощью системной хранимой процедуры **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="9069e-113">The current value of the `Ole Automation Procedures` option can be viewed and changed by using the **sp_configure** system stored procedure.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9069e-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="9069e-114">Examples</span></span>  
 <span data-ttu-id="9069e-115">В следующем примере показан просмотр текущего значения параметра OLE Automation procedures.</span><span class="sxs-lookup"><span data-stu-id="9069e-115">The following example shows how to view the current setting of OLE Automation procedures.</span></span>  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 <span data-ttu-id="9069e-116">В следующем примере показано включение процедур OLE-автоматизации.</span><span class="sxs-lookup"><span data-stu-id="9069e-116">The following example shows how to enable OLE Automation procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9069e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="9069e-117">See Also</span></span>  
 <span data-ttu-id="9069e-118">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9069e-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="9069e-119">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9069e-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="9069e-120">[Настройка контактной зоны](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9069e-120">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 [<span data-ttu-id="9069e-121">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9069e-121">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
