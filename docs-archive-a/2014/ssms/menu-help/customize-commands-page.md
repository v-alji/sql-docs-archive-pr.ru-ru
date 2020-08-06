---
title: Настройка (страница "Команды") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.vs.customizecom.f1
ms.assetid: c8965f2c-51d9-437d-a6f3-8ac2075ede6b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684fb9a6266fafae00b9881eb64a3642e6c98c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733449"
---
# <a name="customize-commands-page"></a><span data-ttu-id="89c24-102">Настройка (страница «Команды»)</span><span class="sxs-lookup"><span data-stu-id="89c24-102">Customize (Commands Page)</span></span>
  <span data-ttu-id="89c24-103">В этом диалоговом окне можно вводить и удалять команды панелей инструментов и меню, а также изменять изображения для кнопок на панели инструментов или команд меню.</span><span class="sxs-lookup"><span data-stu-id="89c24-103">This dialog box enables you to add and remove commands on toolbars and menus as well as change the images used for toolbar buttons or menu commands.</span></span> <span data-ttu-id="89c24-104">Чтобы открыть страницу **Команды** , в меню **Сервис** выберите команду **Настройка** , а затем выберите **Команды**.</span><span class="sxs-lookup"><span data-stu-id="89c24-104">You can access the **Commands** page by clicking **Customize** on the **Tools** menu and then clicking **Commands**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="89c24-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="89c24-105">UI element list</span></span>  
 <span data-ttu-id="89c24-106">**Категории**</span><span class="sxs-lookup"><span data-stu-id="89c24-106">**Categories**</span></span>  
 <span data-ttu-id="89c24-107">Определяет набор команд, отображаемых в списке **Команды** .</span><span class="sxs-lookup"><span data-stu-id="89c24-107">Specifies the set of commands that are displayed in the **Commands** list box.</span></span> <span data-ttu-id="89c24-108">Категории команд формируются на основе заголовков меню, предоставляемых инструментами и конструкторами, реализованными в настоящее время в данной среде.</span><span class="sxs-lookup"><span data-stu-id="89c24-108">The categories of commands are based on menu titles provided by the tools and designers that the environment is currently supporting.</span></span> <span data-ttu-id="89c24-109">Список заголовков динамически меняется, поэтому порядок категорий и заголовков меню изменяется в зависимости от инструмента или конструктора, а также по мере их настройки.</span><span class="sxs-lookup"><span data-stu-id="89c24-109">This list of titles is dynamic so that the order of categories and the menu titles change, depending on the tools and the designer, as well as any customizations made to them.</span></span> <span data-ttu-id="89c24-110">Поэтому два меню различных конструкторов могут иметь одинаковое имя, и один заголовок будет отображаться дважды, но будет содержать различные наборы команд.</span><span class="sxs-lookup"><span data-stu-id="89c24-110">Therefore, it is possible for two menus from different designers to have the same name, so the same title can appear twice but offer different command sets.</span></span>  
  
 <span data-ttu-id="89c24-111">**Команды**</span><span class="sxs-lookup"><span data-stu-id="89c24-111">**Commands**</span></span>  
 <span data-ttu-id="89c24-112">Перечень команд и изображений команд в зависимости от выбранной категории.</span><span class="sxs-lookup"><span data-stu-id="89c24-112">Displays the commands and command images based on the category you selected.</span></span> <span data-ttu-id="89c24-113">Команду можно перетащить в настраиваемую панель инструментов.</span><span class="sxs-lookup"><span data-stu-id="89c24-113">You can drag a command onto the toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="89c24-114">**Изменить выбор**</span><span class="sxs-lookup"><span data-stu-id="89c24-114">**Modify Selection**</span></span>  
 <span data-ttu-id="89c24-115">Перечень команд, с помощью которых можно настроить внешний вид кнопки на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="89c24-115">Displays a list of commands you can use to customize the display of the button on the toolbar.</span></span> <span data-ttu-id="89c24-116">Например, можно изменить изображение или назначить сочетание клавиш, а также включить для данной команды отображение текста вместо изображения.</span><span class="sxs-lookup"><span data-stu-id="89c24-116">For example, you can change the image or accelerator keys, as well as specify whether to display text instead of an image for the command.</span></span> <span data-ttu-id="89c24-117">Эта кнопка доступна, только если на панели инструментов выбрана командная кнопка, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="89c24-117">This button is available after you select a command button on a toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="89c24-118">**Упорядочение команд**</span><span class="sxs-lookup"><span data-stu-id="89c24-118">**Rearrange Commands**</span></span>  
 <span data-ttu-id="89c24-119">Вывод на экран диалогового окна **Упорядочение команд** , в котором можно переименовать, упорядочить, добавить или удалить команды из меню и панелей инструментов, а также изменить изображения кнопок и команд.</span><span class="sxs-lookup"><span data-stu-id="89c24-119">Displays the **Rearrange Commands** dialog box, which allows you to rename, reorder, add, and remove commands on menus and toolbars as well as change button and command images.</span></span>  
  
 <span data-ttu-id="89c24-120">**Клавиатура**</span><span class="sxs-lookup"><span data-stu-id="89c24-120">**Keyboard**</span></span>  
 <span data-ttu-id="89c24-121">Вывод на экран страницы **Клавиатура** диалогового окна **Параметры** , на которой можно назначить сочетания клавиш для вызова команд.</span><span class="sxs-lookup"><span data-stu-id="89c24-121">Displays the **Keyboard** page of the **Options** dialog box so you can specify shortcut key combinations for commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c24-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="89c24-122">See Also</span></span>  
 [<span data-ttu-id="89c24-123">Настройка меню и сочетаний клавиш</span><span class="sxs-lookup"><span data-stu-id="89c24-123">Customize Menus and Shortcut Keys</span></span>](../customize-menus-and-shortcut-keys.md)  
