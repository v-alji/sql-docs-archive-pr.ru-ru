---
title: Публикация выполнения хранимой процедуры в публикации транзакций (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- stored procedures [SQL Server replication], publishing
ms.assetid: 1d3a3525-0bc5-466f-b097-5359dc74432d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44310d45a7049701a6aecfa73301b15b0021ac6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656315"
---
# <a name="publish-the-execution-of-a-stored-procedure-in-a-transactional-publication-sql-server-management-studio"></a><span data-ttu-id="485b2-102">опубликовать выполнение хранимой процедуры в публикации транзакций (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="485b2-102">Publish the Execution of a Stored Procedure in a Transactional Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="485b2-103">Укажите, что выполнение хранимой процедуры (а не просто ее определение) следует опубликовывать в диалоговом окне **Свойства статьи — \<Article>** .</span><span class="sxs-lookup"><span data-stu-id="485b2-103">Specify that the execution of a stored procedure (rather than just its definition) should be published in the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="485b2-104">Это диалоговое окно доступно в мастере создания публикаций и в диалоговом окне **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="485b2-104">This dialog box is available in the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="485b2-105">Дополнительные сведения об использовании мастера и доступе к этому диалоговому окну см. в статьях [Создание публикации](create-a-publication.md) и [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="485b2-105">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
 <span data-ttu-id="485b2-106">Определение процедуры (инструкция CREATE PROCEDURE) реплицируется на подписчик при инициализации подписки. Когда процедура выполняется на издателе, репликация выполняет соответствующую процедуру на подписчике.</span><span class="sxs-lookup"><span data-stu-id="485b2-106">The definition of the procedure (the CREATE PROCEDURE statement) is replicated to the Subscriber when the subscription is initialized; when the procedure is executed at the Publisher, replication executes the corresponding procedure at the Subscriber.</span></span>  
  
### <a name="to-publish-the-execution-of-a-stored-procedure"></a><span data-ttu-id="485b2-107">Публикация выполнения хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="485b2-107">To publish the execution of a stored procedure</span></span>  
  
1.  <span data-ttu-id="485b2-108">Выберите хранимую процедуру на странице **Статьи** мастера создания публикаций или в диалоговом окне **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="485b2-108">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a stored procedure.</span></span>  
  
2.  <span data-ttu-id="485b2-109">Щелкните **Свойства статьи**, а затем щелкните **Задать свойства выделенной хранимой процедуры**.</span><span class="sxs-lookup"><span data-stu-id="485b2-109">Click **Article Properties**, and then click **Set Properties of Highlighted Stored Procedure**.</span></span>  
  
3.  <span data-ttu-id="485b2-110">В диалоговом окне **Свойства статьи —\<Article>** укажите одно из следующих значений для параметра **Репликация**.</span><span class="sxs-lookup"><span data-stu-id="485b2-110">In the **Article Properties - \<Article>** dialog box, specify one of the following values for the **Replicate** option:</span></span>  
  
    -   <span data-ttu-id="485b2-111">**Выполнение хранимой процедуры**</span><span class="sxs-lookup"><span data-stu-id="485b2-111">**Execution of the stored procedure**</span></span>  
  
    -   <span data-ttu-id="485b2-112">**Выполнение в сериализованной транзакции хранимой процедуры**</span><span class="sxs-lookup"><span data-stu-id="485b2-112">**Execution in a serialized transaction of the SP**</span></span>  
  
         <span data-ttu-id="485b2-113">Это рекомендуемый параметр, поскольку он реплицирует выполнение процедуры только в случае ее выполнения в контексте сериализуемой транзакции.</span><span class="sxs-lookup"><span data-stu-id="485b2-113">This is the recommended option, because it replicates the procedure execution only if the procedure is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="485b2-114">При выполнении хранимой процедуры вне сериализуемой транзакции изменения, вносимые в данные опубликованных таблиц, реплицируются как ряды инструкций языка обработки данных.</span><span class="sxs-lookup"><span data-stu-id="485b2-114">If the stored procedure is executed outside of a serializable transaction, changes to data in published tables are replicated as a series of data manipulation language (DML) statements.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="485b2-115">Если вы находитесь в диалоговом окне **Свойства публикации — \<Publication>** , нажмите кнопку **OK**, чтобы сохранить результаты и закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="485b2-115">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="485b2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="485b2-116">See Also</span></span>  
 [<span data-ttu-id="485b2-117">Публикация выполнения хранимых процедур в репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="485b2-117">Publishing Stored Procedure Execution in Transactional Replication</span></span>](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md)  
  
  
