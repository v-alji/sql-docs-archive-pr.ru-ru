---
title: Управление табличными пространствами Oracle | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3624aed38a7a5bf75e0c0807aa8d3657156264f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733925"
---
# <a name="manage-oracle-tablespaces"></a><span data-ttu-id="0fdf9-102">Управление табличными пространствами Oracle</span><span class="sxs-lookup"><span data-stu-id="0fdf9-102">Manage Oracle Tablespaces</span></span>
  <span data-ttu-id="0fdf9-103">Табличное пространство — это единица хранилища базы данных, приблизительно эквивалентная группе файлов в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fdf9-103">A tablespace is a unit of database storage that is roughly equivalent to a file group in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0fdf9-104">Табличные пространства предоставляют возможности хранения и управления объектами баз данных в рамках индивидуальных групп.</span><span class="sxs-lookup"><span data-stu-id="0fdf9-104">Tablespaces allow storage and management of database objects within individual groups.</span></span> <span data-ttu-id="0fdf9-105">Дополнительные сведения см. в документации Oracle.</span><span class="sxs-lookup"><span data-stu-id="0fdf9-105">For more information, see the Oracle documentation.</span></span>  
  
 <span data-ttu-id="0fdf9-106">При настройке таблицы как части публикации Oracle можно при желании указать, что существующее табличное пространство Oracle будет использоваться для хранения информации о ходе репликации.</span><span class="sxs-lookup"><span data-stu-id="0fdf9-106">When you configure a table as part of an Oracle publication, you can optionally specify an existing Oracle tablespace to be used when storing replication logging information.</span></span> <span data-ttu-id="0fdf9-107">В противном случае табличным пространством для объектов репликации будет табличное пространство по умолчанию, связанное с административной пользовательской схемой репликации, которая была настроена при настройке издателя.</span><span class="sxs-lookup"><span data-stu-id="0fdf9-107">If unspecified, the tablespace for the replication objects is the default tablespace associated with the replication administrative user schema that was configured when configuring the Publisher.</span></span>  
  
 <span data-ttu-id="0fdf9-108">**Указание табличного пространства для таблицы регистрации статей**:</span><span class="sxs-lookup"><span data-stu-id="0fdf9-108">**To specify a tablespace for an article logging table**:</span></span>  
  
-   <span data-ttu-id="0fdf9-109">Задайте табличное пространство в диалоговом окне **Свойства статьи** .</span><span class="sxs-lookup"><span data-stu-id="0fdf9-109">Specify a tablespace in the **Article Properties** dialog box.</span></span> <span data-ttu-id="0fdf9-110">Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0fdf9-110">For more information about accessing this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="0fdf9-111">Используйте [sp_changearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0fdf9-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span></span> <span data-ttu-id="0fdf9-112">Чтобы использовать **sp_changearticle**, укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="0fdf9-112">To use **sp_changearticle**, specify the following:</span></span>  
  
    -   <span data-ttu-id="0fdf9-113">Имя издателя Oracle для параметра **@publisher** .</span><span class="sxs-lookup"><span data-stu-id="0fdf9-113">The name of the Oracle Publisher for the parameter **@publisher**.</span></span>  
  
    -   <span data-ttu-id="0fdf9-114">Имя публикации Oracle для параметра **@publication** .</span><span class="sxs-lookup"><span data-stu-id="0fdf9-114">The name of the Oracle publication for the parameter **@publication**.</span></span>  
  
    -   <span data-ttu-id="0fdf9-115">Имя статьи для параметра **@article** .</span><span class="sxs-lookup"><span data-stu-id="0fdf9-115">The name of the article for the parameter **@article**.</span></span>  
  
    -   <span data-ttu-id="0fdf9-116">Значение "табличное пространство" для параметра **@property** .</span><span class="sxs-lookup"><span data-stu-id="0fdf9-116">A value of 'tablespace' for the parameter **@property**.</span></span>  
  
    -   <span data-ttu-id="0fdf9-117">Имя табличного пространства для параметра **@value** .</span><span class="sxs-lookup"><span data-stu-id="0fdf9-117">The name of the tablespace for the parameter **@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fdf9-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fdf9-118">See Also</span></span>  
 <span data-ttu-id="0fdf9-119">[Настройка издателя Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="0fdf9-119">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="0fdf9-120">Объекты, создаваемые в издателе Oracle</span><span class="sxs-lookup"><span data-stu-id="0fdf9-120">Objects Created on the Oracle Publisher</span></span>](objects-created-on-the-oracle-publisher.md)  
  
  
