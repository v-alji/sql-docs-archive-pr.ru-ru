---
title: Открытие шаблона | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- templates [Transact-SQL], opening
- opening templates
ms.assetid: 605b0f4c-5ba1-4249-ad1c-6341df77cd7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 43b75d68fafea759e4d7873c1fb738d7964dcf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665733"
---
# <a name="open-a-template"></a><span data-ttu-id="76107-102">Открытие шаблона</span><span class="sxs-lookup"><span data-stu-id="76107-102">Open a Template</span></span>
  <span data-ttu-id="76107-103">Можно открыть шаблон в обозревателе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="76107-103">You can open a template from Template Explorer.</span></span>  
  
## <a name="to-open-a-template-from-template-explorer"></a><span data-ttu-id="76107-104">Открытие шаблона в Обозревателе шаблонов</span><span class="sxs-lookup"><span data-stu-id="76107-104">To open a template from Template Explorer</span></span>  
 <span data-ttu-id="76107-105">Можно открыть шаблоны в обозревателе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="76107-105">You can open templates from the Template Explorer.</span></span>  
  
1.  <span data-ttu-id="76107-106">Чтобы открыть обозреватель шаблонов, выберите пункт **Обозреватель шаблонов** в меню **Вид**.</span><span class="sxs-lookup"><span data-stu-id="76107-106">To open Template Explorer, on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="76107-107">В списке категорий шаблонов разверните категорию, в которой находится нужный шаблон.</span><span class="sxs-lookup"><span data-stu-id="76107-107">In the list of template categories, expand the category that contains the template you want to open.</span></span>  
  
3.  <span data-ttu-id="76107-108">Предусмотрены три способа открыть шаблон.</span><span class="sxs-lookup"><span data-stu-id="76107-108">There are three ways to open the template:</span></span>  
  
    1.  <span data-ttu-id="76107-109">Дважды щелкните шаблон, чтобы открыть его в окне редактора кода.</span><span class="sxs-lookup"><span data-stu-id="76107-109">Double-click the template to open it in a code editor window.</span></span>  
  
    2.  <span data-ttu-id="76107-110">Щелкните шаблон правой кнопкой мыши и выберите в меню пункт **Открыть** , чтобы открыть его в окне редактора кода.</span><span class="sxs-lookup"><span data-stu-id="76107-110">Right-click the template and select **Open** to open it in a code editor window.</span></span>  
  
    3.  <span data-ttu-id="76107-111">Перетащите шаблон в окно редактора кода, чтобы добавить код шаблона в содержимое окна редактора.</span><span class="sxs-lookup"><span data-stu-id="76107-111">Drag the template into a code editor window to add the template code to the contents of the editor window.</span></span>  
  
 <span data-ttu-id="76107-112">Нужные значения аргументов открытого шаблона задаются в окне **Замена параметров шаблона** .</span><span class="sxs-lookup"><span data-stu-id="76107-112">After the template is open, use the **Replace Template Parameters** dialog box to replace the template parameters with your values.</span></span>  
  
 <span data-ttu-id="76107-113">При открытии шаблона запускается новое окно редактора. Окно редактора откроется с учетными данными текущего активного соединения.</span><span class="sxs-lookup"><span data-stu-id="76107-113">If opening a template launches a new editor window, the window will open with the credentials of the current active connection.</span></span> <span data-ttu-id="76107-114">Например, если выбрать экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в обозревателе объектов при открытии шаблона CREATE DATABASE, откроется новое окно редактора кода с подключением к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="76107-114">For example, if you are focused on an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in Object Explorer when you open the CREATE DATABASE template, a new editor window will be opened using a connection to that instance.</span></span> <span data-ttu-id="76107-115">Если активных соединений нет, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] представит диалоговое окно входа.</span><span class="sxs-lookup"><span data-stu-id="76107-115">If there is no active connection, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] will present a login dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76107-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="76107-116">See Also</span></span>  
 <span data-ttu-id="76107-117">[Обозреватель шаблонов](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="76107-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="76107-118">Замена параметров шаблона</span><span class="sxs-lookup"><span data-stu-id="76107-118">Replace Template Parameters</span></span>](replace-template-parameters.md)  
  
  
