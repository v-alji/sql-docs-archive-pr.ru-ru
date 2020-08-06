---
title: Включение удаленного издателя на распространителе (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- remote Distributors [SQL Server replication]
- Publishers [SQL Server replication]
ms.assetid: 6f8e2831-5c45-4e39-8e51-d37e2813cf3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 06c85924731b79e8b3c79cfbcc354b5bedf69b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655620"
---
# <a name="enable-a-remote-publisher-at-a-distributor-sql-server-management-studio"></a><span data-ttu-id="daa00-102">включить удаленный издатель на распространителе (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="daa00-102">Enable a Remote Publisher at a Distributor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="daa00-103">Предоставьте издателю разрешение использовать удаленный распространитель на странице **Издатели** .</span><span class="sxs-lookup"><span data-stu-id="daa00-103">Enable a Publisher to use a remote Distributor on the **Publishers** page.</span></span> <span data-ttu-id="daa00-104">Эта страница доступна в мастере настройки распространителя и диалоговом окне **Свойства распространителя — \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="daa00-104">This page is available in the Configure Distribution Wizard and the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="daa00-105">Дополнительные сведения об использовании мастера и о доступе к этому диалоговому окну см. в статьях [Настройка публикации и распространения](configure-publishing-and-distribution.md) и [Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="daa00-105">For more information about using the wizard and accessing the dialog box, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-enable-a-publisher-in-the-configure-distribution-wizard"></a><span data-ttu-id="daa00-106">Включение издателя в мастере настройки распространителя</span><span class="sxs-lookup"><span data-stu-id="daa00-106">To enable a Publisher in the Configure Distribution Wizard</span></span>  
  
1.  <span data-ttu-id="daa00-107">На странице **Издатели** мастера настройки распространителя щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="daa00-107">On the **Publishers** page of the Configure Distribution Wizard, click **Add**.</span></span>  
  
2.  <span data-ttu-id="daa00-108">Щелкните **Добавить издатель SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="daa00-108">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="daa00-109">Сведения о том, как разрешить издателю Oracle использовать распространитель, см. в разделе [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="daa00-109">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="daa00-110">В диалоговом окне **Соединение с сервером** укажите сведения о соединении для издателя, который будет использовать удаленный распространитель, а затем щелкните **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="daa00-110">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="daa00-111">На странице **Пароль распространителя** в текстовых полях **Пароль** и **Подтверждение пароля** укажите надежный пароль для учетной записи **distributor_admin** , используемой системой репликации, чтобы подключить издателя к распространителю для выполнения административных задач.</span><span class="sxs-lookup"><span data-stu-id="daa00-111">On the **Distributor Password** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="daa00-112">Для просмотра и изменения параметров издателя нажмите кнопку свойств с многоточием ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="daa00-112">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-enable-a-publisher-in-the-distributor-properties-dialog-box"></a><span data-ttu-id="daa00-113">Включение издателя в диалоговом окне «Свойства распространителя»</span><span class="sxs-lookup"><span data-stu-id="daa00-113">To enable a Publisher in the Distributor Properties dialog box</span></span>  
  
1.  <span data-ttu-id="daa00-114">На странице **Издатели** диалогового окна **Свойства распространителя — \<Distributor>** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="daa00-114">On the **Publishers** page of the **Distributor Properties - \<Distributor>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="daa00-115">Щелкните **Добавить издатель SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="daa00-115">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="daa00-116">Сведения о том, как разрешить издателю Oracle использовать распространитель, см. в разделе [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="daa00-116">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="daa00-117">В диалоговом окне **Соединение с сервером** укажите сведения о соединении для издателя, который будет использовать удаленный распространитель, а затем щелкните **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="daa00-117">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="daa00-118">На странице **Издатели** в текстовых полях **Пароль** и **Подтверждение пароля** укажите надежный пароль для учетной записи **distributor_admin** , используемой системой репликации, чтобы подключить издатель к распространителю для выполнения административных задач.</span><span class="sxs-lookup"><span data-stu-id="daa00-118">On the **Publishers** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="daa00-119">Для просмотра и изменения параметров издателя нажмите кнопку свойств с многоточием ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="daa00-119">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="daa00-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="daa00-120">See Also</span></span>  
 <span data-ttu-id="daa00-121">[Настройка публикации и распространения](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="daa00-121">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="daa00-122">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="daa00-122">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="daa00-123">Защита распространителя</span><span class="sxs-lookup"><span data-stu-id="daa00-123">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
