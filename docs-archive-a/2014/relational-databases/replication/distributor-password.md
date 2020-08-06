---
title: Пароль распространителя | Документация Майкрософт
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributorpassword.f1
ms.assetid: 52787c5e-c9ef-440e-a000-0787111b7dbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 63e635903793bfa63d12b8a4cd2985178f9c4837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655634"
---
# <a name="distributor-password"></a><span data-ttu-id="48b03-102">Пароль распространителя</span><span class="sxs-lookup"><span data-stu-id="48b03-102">Distributor Password</span></span>
  <span data-ttu-id="48b03-103">Если на странице **Издатели** данного мастера пользователь включил одного или нескольких издателей для использования данного сервера в качестве удаленного распространителя, то необходимо задать пароль для соединения, устанавливаемого репликацией, между издателем и удаленным распространителем, используя имя входа **distributor_admin** .</span><span class="sxs-lookup"><span data-stu-id="48b03-103">If, on the **Publishers** page of this wizard, you enabled one or more Publishers to use this server as a remote Distributor, you must specify a password for the connection replication makes between the Publisher and the remote Distributor using the **distributor_admin** login.</span></span> <span data-ttu-id="48b03-104">Тот же пароль необходимо ввести для каждого издателя, использующего этот удаленный распространитель, на странице **Административный пароль** мастера создания публикаций или мастера настройки распространения.</span><span class="sxs-lookup"><span data-stu-id="48b03-104">The same password must be entered for each Publisher that uses this remote Distributor on the **Administrative Password** page of the New Publication Wizard or the Configure Distribution Wizard.</span></span> <span data-ttu-id="48b03-105">Дополнительные сведения о безопасности распространителей см. в разделе [Защита распространителя](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="48b03-105">For more information on security for Distributors, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="48b03-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="48b03-106">Options</span></span>  
 <span data-ttu-id="48b03-107">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="48b03-107">**Password**</span></span>  
 <span data-ttu-id="48b03-108">Введите надежный пароль для соединения между издателем и удаленным распространителем.</span><span class="sxs-lookup"><span data-stu-id="48b03-108">Enter a strong password for the connection between the Publisher and the remote Distributor.</span></span>  
  
 <span data-ttu-id="48b03-109">**Подтвердите пароль**</span><span class="sxs-lookup"><span data-stu-id="48b03-109">**Confirm Password**</span></span>  
 <span data-ttu-id="48b03-110">Повторно введите пароль, чтобы подтвердить правильность ввода.</span><span class="sxs-lookup"><span data-stu-id="48b03-110">Re-enter the password to confirm it was entered correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b03-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="48b03-111">See Also</span></span>  
 <span data-ttu-id="48b03-112">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="48b03-112">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="48b03-113">Настройка публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="48b03-113">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
