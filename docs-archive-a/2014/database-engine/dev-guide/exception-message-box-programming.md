---
title: Программирование окна сообщения об исключении | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751435"
---
# <a name="exception-message-box-programming"></a><span data-ttu-id="7dd17-102">Программирование окон сообщений об исключениях</span><span class="sxs-lookup"><span data-stu-id="7dd17-102">Exception Message Box Programming</span></span>
  <span data-ttu-id="7dd17-103">Окно сообщения об исключении — это программный интерфейс, который устанавливается и используется [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] графическими компонентами.</span><span class="sxs-lookup"><span data-stu-id="7dd17-103">The exception message box is a programmatic interface that is installed with and used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] graphical components.</span></span> <span data-ttu-id="7dd17-104">Окно сообщения об исключении является поддерживаемой управляемой сборкой, которая используется в приложении, чтобы обеспечить в приложении более полное управление сообщениями и дать пользователям возможность сохранять содержимое сообщения об ошибке для последующего просмотра сообщений и получения помощи при работе с ними.</span><span class="sxs-lookup"><span data-stu-id="7dd17-104">The exception message box is a supported managed assembly that you can use in your applications to provide significantly more control over the messaging experience and to give your users the options to save error message content for later reference and to get help on messages.</span></span> <span data-ttu-id="7dd17-105">Поскольку окно сообщения об исключении устанавливается всеми выпусками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], за исключением [!INCLUDE[ssEW](../../includes/ssew-md.md)], его можно использовать без дополнительной настройки на любом компьютере, на котором установлены клиентские компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd17-105">Because the exception message box is installed by all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssEW](../../includes/ssew-md.md)], you can use it with no additional configuration on any computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client components have been installed.</span></span>  
  
 <span data-ttu-id="7dd17-106">Класс <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> в пространстве имен <xref:Microsoft.SqlServer.MessageBox> имеет все возможности класса <xref:System.Windows.Forms.MessageBox> и некоторые дополнительные.</span><span class="sxs-lookup"><span data-stu-id="7dd17-106">The <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in the <xref:Microsoft.SqlServer.MessageBox> namespace has all the functionality of the <xref:System.Windows.Forms.MessageBox> class and more.</span></span> <span data-ttu-id="7dd17-107">Класс <xref:System.Windows.Forms.MessageBox> идеально подходит для всех задач, в которых используется класс <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>, он разработан для эффективного управления исключениями управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7dd17-107">Ideal for any tasks for which <xref:System.Windows.Forms.MessageBox> may be used, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> is designed to elegantly handle managed code exceptions.</span></span> <span data-ttu-id="7dd17-108">Окно сообщения об исключении выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7dd17-108">The exception message box allows you to do the following:</span></span>  
  
-   <span data-ttu-id="7dd17-109">Обеспечивает настраиваемый текст для кнопок (не более пяти).</span><span class="sxs-lookup"><span data-stu-id="7dd17-109">Provide customized button text for up to five buttons.</span></span> <span data-ttu-id="7dd17-110">Кнопки и диалоговые окна автоматически меняют размер в зависимости от длины текста.</span><span class="sxs-lookup"><span data-stu-id="7dd17-110">Buttons and the dialog box resize automatically for different text lengths.</span></span>  
  
-   <span data-ttu-id="7dd17-111">Дает пользователям возможность легко копировать заголовок сообщения, текст, текст кнопок и ссылки на разделы справки (если таковые имеются) в буфер обмена или отправлять эти сведения в электронных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7dd17-111">Allow users to easily copy the message title, text, button text, and help links (if any) to the Clipboard or send this information in an e-mail message.</span></span>  
  
-   <span data-ttu-id="7dd17-112">Отображает все базовые исключения и ошибки в иерархическом дереве связей, когда пользователи щелкают **Дополнительные сведения**.</span><span class="sxs-lookup"><span data-stu-id="7dd17-112">Display all underlying exceptions and errors in a hierarchical relationship tree when users click **Additional Information**.</span></span>  
  
-   <span data-ttu-id="7dd17-113">Дает пользователям возможность решать, нужно ли отображать сообщение при повторении одного и того же исключения.</span><span class="sxs-lookup"><span data-stu-id="7dd17-113">Allow users to decide whether to display the message when the same exception occurs again.</span></span>  
  
-   <span data-ttu-id="7dd17-114">Обеспечивает доступ к справке в Интернете с помощью ссылки на раздел справки, связанный с тем или иным исключением.</span><span class="sxs-lookup"><span data-stu-id="7dd17-114">Access an online help system by using a help link associated with the exception.</span></span>  
  
 <span data-ttu-id="7dd17-115">Дополнительные сведения см. в разделе [сообщение об исключении программы](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span><span class="sxs-lookup"><span data-stu-id="7dd17-115">For more information, see [Program Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span></span>  
  
  
