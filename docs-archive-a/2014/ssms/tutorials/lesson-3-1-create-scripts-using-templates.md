---
title: Создание скриптов на основе шаблонов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ed48014c-3fc9-48ff-8c0f-8d1822195f14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b404ecc505e93c302e4c737f9c0b0161d9015519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733409"
---
# <a name="create-scripts-using-templates"></a><span data-ttu-id="52d2a-102">Создание скриптов на основе шаблонов</span><span class="sxs-lookup"><span data-stu-id="52d2a-102">Create Scripts Using Templates</span></span>
  <span data-ttu-id="52d2a-103">Среда Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] предлагает большое число шаблонов скриптов, содержащих инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , предназначенные для решения многих типовых задач.</span><span class="sxs-lookup"><span data-stu-id="52d2a-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides a large number of script templates containing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for many common tasks.</span></span> <span data-ttu-id="52d2a-104">Эти шаблоны содержат параметры, значения которых вводятся пользователем, такие как имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="52d2a-104">These templates contain parameters for the user-provided values such as a table name.</span></span> <span data-ttu-id="52d2a-105">Используя эти параметры, можно ввести имя только один раз, а затем автоматически скопировать его во все требуемые позиции в скрипте.</span><span class="sxs-lookup"><span data-stu-id="52d2a-105">Using the parameters, you can type the name once and then automatically copy the name to all the necessary locations within the script.</span></span> <span data-ttu-id="52d2a-106">Можно создавать собственные пользовательские шаблоны для поддержки скриптов, которые приходится писать чаще всего.</span><span class="sxs-lookup"><span data-stu-id="52d2a-106">You can write your own custom templates to support the scripts that you write most often.</span></span> <span data-ttu-id="52d2a-107">Кроме того, можно реорганизовать дерево шаблонов, перемещая шаблоны или создавая новые папки для их хранения.</span><span class="sxs-lookup"><span data-stu-id="52d2a-107">You can also reorganize the template tree, moving templates or creating new folders to hold the templates.</span></span> <span data-ttu-id="52d2a-108">В следующей практической работе с помощью шаблона будет создана база данных с указанием шаблона параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="52d2a-108">In the following practice, you will use a template to create a database, specifying collation template.</span></span>  
  
## <a name="using-templates"></a><span data-ttu-id="52d2a-109">Использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="52d2a-109">Using Templates</span></span>  
  
#### <a name="to-create-a-script-using-a-template"></a><span data-ttu-id="52d2a-110">Создание скрипта на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="52d2a-110">To create a script using a template</span></span>  
  
1.  <span data-ttu-id="52d2a-111">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]в меню **Вид** выберите пункт **Обозреватель шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="52d2a-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="52d2a-112">Шаблоны в обозревателе шаблонов распределены по группам.</span><span class="sxs-lookup"><span data-stu-id="52d2a-112">The templates in Template Explorer are organized into groups.</span></span> <span data-ttu-id="52d2a-113">Раскройте узел **База данных**, а затем дважды щелкните элемент **Создание базы данных**.</span><span class="sxs-lookup"><span data-stu-id="52d2a-113">Expand **Database**, and then double-click **Create Database**.</span></span>  
  
3.  <span data-ttu-id="52d2a-114">В диалоговом окне **Подключиться к ядру СУБД** введите сведения о соединении и нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="52d2a-114">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="52d2a-115">Откроется новое окно редактора запросов, в котором приводится содержимое шаблона **Создание базы данных** .</span><span class="sxs-lookup"><span data-stu-id="52d2a-115">A new Query Editor window opens, containing the contents of the **Create Database** template.</span></span>  
  
4.  <span data-ttu-id="52d2a-116">В меню **Запрос** выберите пункт **Указать значения для параметров шаблона**.</span><span class="sxs-lookup"><span data-stu-id="52d2a-116">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="52d2a-117">В диалоговом окне **Задание значений для параметров шаблона** столбец **Значение** содержит предлагаемое значение параметра **Имя базы данных** .</span><span class="sxs-lookup"><span data-stu-id="52d2a-117">In the **Specify Values for Template Parameters** dialog box, the **Value** column contains a suggested value for the **Database_Name** parameter.</span></span> <span data-ttu-id="52d2a-118">В поле параметра **Имя базы данных** введите **Маркетинг**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="52d2a-118">In the **Database Name** parameter box, type **Marketing**, and then click **OK**.</span></span> <span data-ttu-id="52d2a-119">Обратите внимание, что имя «Маркетинг» автоматически вставляется в скрипт в нескольких местах.</span><span class="sxs-lookup"><span data-stu-id="52d2a-119">Note how "Marketing" is inserted into the script in several locations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="52d2a-120">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="52d2a-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="52d2a-121">Создание пользовательских шаблонов</span><span class="sxs-lookup"><span data-stu-id="52d2a-121">Create Custom Templates</span></span>](lesson-3-2-create-custom-templates.md)  
  
  
