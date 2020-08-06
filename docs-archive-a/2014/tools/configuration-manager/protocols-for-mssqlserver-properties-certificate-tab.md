---
title: Протоколы для свойств MSSQLSERVER (вкладка "Сертификат") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.computermgr.cert.general.f1
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 776addd6-25f3-4875-9a71-064035787090
author: stevestein
ms.author: sstein
ms.openlocfilehash: 020d33eba7621f877f8622ca89dbd26a071f16a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737298"
---
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a><span data-ttu-id="740ec-102">Протоколы для свойств MSSQLSERVER (вкладка «Сертификат»)</span><span class="sxs-lookup"><span data-stu-id="740ec-102">Protocols for MSSQLSERVER Properties (Certificate Tab)</span></span>
  <span data-ttu-id="740ec-103">Используйте вкладку **Сертификат** в диалоговом окне **Протоколы для свойств MSSQLSERVER**, чтобы выбрать сертификат для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]или просмотреть свойства сертификата.</span><span class="sxs-lookup"><span data-stu-id="740ec-103">Use the **Certificate** tab on the **Protocols for MSSQLSERVER Properties** dialog box to select a certificate for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or to view the properties of a certificate.</span></span> <span data-ttu-id="740ec-104">До выбора сертификата все поля остаются пустыми.</span><span class="sxs-lookup"><span data-stu-id="740ec-104">All fields are blank until a certificate is selected.</span></span>  
  
 <span data-ttu-id="740ec-105">Сертификаты хранятся локально на пользовательских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="740ec-105">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="740ec-106">Чтобы загрузить сертификат для использования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], необходимо запустить диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с той же учетной записью пользователя, что и служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="740ec-106">To load a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="740ec-107">Заголовок страницы</span><span class="sxs-lookup"><span data-stu-id="740ec-107">Page Header</span></span>  
 <span data-ttu-id="740ec-108">**View** (Вид)</span><span class="sxs-lookup"><span data-stu-id="740ec-108">**View**</span></span>  
 <span data-ttu-id="740ec-109">Обеспечивает доступ к дополнительным данным сертификата.</span><span class="sxs-lookup"><span data-stu-id="740ec-109">Provides access to additional details on the certificate.</span></span> <span data-ttu-id="740ec-110">Недоступно до тех пор, пока сертификат не выбран в поле **Сертификат** .</span><span class="sxs-lookup"><span data-stu-id="740ec-110">Not available until a certificate is selected in the **Certificate** box.</span></span> <span data-ttu-id="740ec-111">Дополнительные сведения о данных сертификата см. в документации по [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="740ec-111">For additional information on certificate details, see your [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
 <span data-ttu-id="740ec-112">**Clear**</span><span class="sxs-lookup"><span data-stu-id="740ec-112">**Clear**</span></span>  
 <span data-ttu-id="740ec-113">Отменяет выбор в поле **Сертификат** .</span><span class="sxs-lookup"><span data-stu-id="740ec-113">Removes the selection from the **Certificate** box.</span></span>  
  
 <span data-ttu-id="740ec-114">**Сертификат**</span><span class="sxs-lookup"><span data-stu-id="740ec-114">**Certificate**</span></span>  
 <span data-ttu-id="740ec-115">Имя сертификата определяется поставщиком безопасности.</span><span class="sxs-lookup"><span data-stu-id="740ec-115">Name of certificate as determined by security provider.</span></span> <span data-ttu-id="740ec-116">Выберите сертификат, чтобы просмотреть данные в сетке свойств.</span><span class="sxs-lookup"><span data-stu-id="740ec-116">Select a certificate to see the details in the properties grid.</span></span>  
  
## <a name="options"></a><span data-ttu-id="740ec-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="740ec-117">Options</span></span>  
 <span data-ttu-id="740ec-118">Срок действия</span><span class="sxs-lookup"><span data-stu-id="740ec-118">Expiration Date</span></span>  
 <span data-ttu-id="740ec-119">Дата окончания периода, в течение которого сертификат действителен.</span><span class="sxs-lookup"><span data-stu-id="740ec-119">The final date for the period in which the certificate is valid.</span></span>  
  
 <span data-ttu-id="740ec-120">Понятное имя</span><span class="sxs-lookup"><span data-stu-id="740ec-120">Friendly Name</span></span>  
 <span data-ttu-id="740ec-121">Понятное или общее имя для физического лица или центра сертификации, которому выдан сертификат.</span><span class="sxs-lookup"><span data-stu-id="740ec-121">A friendly or common name for the individual or certification authority to whom the certificate is issued.</span></span>  
  
 <span data-ttu-id="740ec-122">Кем выдан</span><span class="sxs-lookup"><span data-stu-id="740ec-122">Issued By</span></span>  
 <span data-ttu-id="740ec-123">Сведения, относящиеся к центру сертификации, выдавшему сертификат.</span><span class="sxs-lookup"><span data-stu-id="740ec-123">Information regarding the certification authority that issued the certificate.</span></span>  
  
 <span data-ttu-id="740ec-124">Кому выдан</span><span class="sxs-lookup"><span data-stu-id="740ec-124">Issued To</span></span>  
 <span data-ttu-id="740ec-125">Сведения, относящиеся к получателю сертификата.</span><span class="sxs-lookup"><span data-stu-id="740ec-125">Information regarding the recipient of the certificate.</span></span>  
  
  
