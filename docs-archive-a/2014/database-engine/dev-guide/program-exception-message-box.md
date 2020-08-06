---
title: Окно сообщения об исключении программы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- exception message box [SQL Server]
- displaying exception message box
ms.assetid: c771985b-149c-459a-b3cb-7b15fde01150
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9d49bdf8c73f86b2c334018d40510b4ae67c85ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750128"
---
# <a name="program-exception-message-box"></a><span data-ttu-id="ee607-102">Выведение окна сообщения об исключении программы</span><span class="sxs-lookup"><span data-stu-id="ee607-102">Program Exception Message Box</span></span>
  <span data-ttu-id="ee607-103">Можно воспользоваться окном сообщения об исключении в приложениях, чтобы предоставить значительно больше возможностей управления информированием, чем в классе <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="ee607-103">You can use the exception message box in your applications to provide significantly more control over the messaging experience than is provided by the <xref:System.Windows.Forms.MessageBox> class.</span></span> <span data-ttu-id="ee607-104">Дополнительные сведения см. в разделе [программирование окна сообщений об исключениях](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span><span class="sxs-lookup"><span data-stu-id="ee607-104">For more information, see [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span></span> <span data-ttu-id="ee607-105">Сведения о том, как получить и развернуть библиотеку DLL окна сообщений об исключениях, см. в разделе [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span><span class="sxs-lookup"><span data-stu-id="ee607-105">For information about how to obtain and deploy the exception message box .dll, see [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="ee607-106">Процедура</span><span class="sxs-lookup"><span data-stu-id="ee607-106">Procedure</span></span>  
  
#### <a name="to-handle-an-exception-by-using-the-exception-message-box"></a><span data-ttu-id="ee607-107">Обработка исключения с помощью окна сообщения об исключении</span><span class="sxs-lookup"><span data-stu-id="ee607-107">To handle an exception by using the exception message box</span></span>  
  
1.  <span data-ttu-id="ee607-108">Добавьте в проект управляемого кода ссылку на сборку Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="ee607-108">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="ee607-109">Используемых Добавьте `using` директиву (C#) или `Imports` ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) для использования <xref:Microsoft.SqlServer.MessageBox> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ee607-109">(Optional) Add a `using` (C#) or `Imports` ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="ee607-110">Создайте блок try-catch для обработки ожидаемого исключения.</span><span class="sxs-lookup"><span data-stu-id="ee607-110">Create a try-catch block to handle the anticipated exception.</span></span>  
  
4.  <span data-ttu-id="ee607-111">В блоке `catch` создайте экземпляр класса <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="ee607-111">Within the `catch` block, create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="ee607-112">Передайте <xref:System.Exception> объект, обрабатываемый `try` - `catch` блоком.</span><span class="sxs-lookup"><span data-stu-id="ee607-112">Pass the <xref:System.Exception> object handled by the `try`-`catch` block.</span></span>  
  
5.  <span data-ttu-id="ee607-113">(Необязательно) Задайте одно или несколько из следующих свойств <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox></span><span class="sxs-lookup"><span data-stu-id="ee607-113">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="ee607-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Перечисление, указывающее кнопки, отображаемые в окне сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>Перечисление, указывающее кнопку по умолчанию для окна сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Перечисление, используемое для управления другим поведением окна сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Перечисление, указывающее символ, отображаемый в окне сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
6.  <span data-ttu-id="ee607-118">Вызовите метод <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="ee607-118">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="ee607-119">Передайте родительское окно, к которому относится окно сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-119">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="ee607-120">Отметьте возвращаемое значение перечисления <xref:System.Windows.Forms.DialogResult>, если требуется определить, какую кнопку нажал пользователь (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ee607-120">(Optional) Note the value of returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-without-an-exception"></a><span data-ttu-id="ee607-121">Отображение окна сообщения об исключении без самого исключения</span><span class="sxs-lookup"><span data-stu-id="ee607-121">To display the exception message box without an exception</span></span>  
  
1.  <span data-ttu-id="ee607-122">Добавьте в проект управляемого кода ссылку на сборку Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="ee607-122">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="ee607-123">Используемых Добавьте `using` директиву (C#) или `Imports` (Visual Basic .NET) для использования <xref:Microsoft.SqlServer.MessageBox> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ee607-123">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="ee607-124">Создайте экземпляр класса <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="ee607-124">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="ee607-125">Передайте текст сообщения как <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ee607-125">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="ee607-126">(Необязательно) Задайте одно или несколько из следующих свойств <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox></span><span class="sxs-lookup"><span data-stu-id="ee607-126">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="ee607-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Перечисление, указывающее кнопки, отображаемые в окне сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> — заголовок диалогового окна для окна сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialog box caption of the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>Перечисление, указывающее кнопку по умолчанию для диалогового окна сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the dialog box of the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Перечисление, используемое для управления другим поведением окна сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="ee607-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Перечисление, указывающее символ, отображаемый в окне сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
5.  <span data-ttu-id="ee607-132">Вызовите метод <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="ee607-132">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="ee607-133">Передайте родительское окно, к которому относится окно сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-133">Pass the parent window to which the exception message box belongs.</span></span>  
  
6.  <span data-ttu-id="ee607-134">(Необязательно) Какую из кнопок нажал пользователь, можно определить, проверив значение возвращенного перечисления <xref:System.Windows.Forms.DialogResult>.</span><span class="sxs-lookup"><span data-stu-id="ee607-134">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-with-customized-buttons"></a><span data-ttu-id="ee607-135">Отображение окна сообщения об исключении с пользовательскими кнопками</span><span class="sxs-lookup"><span data-stu-id="ee607-135">To display the exception message box with customized buttons</span></span>  
  
1.  <span data-ttu-id="ee607-136">Добавьте в проект управляемого кода ссылку на сборку Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="ee607-136">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="ee607-137">Используемых Добавьте `using` директиву (C#) или `Imports` (Visual Basic .NET) для использования <xref:Microsoft.SqlServer.MessageBox> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ee607-137">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="ee607-138">Создайте экземпляр класса <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> одним из двух следующих способов.</span><span class="sxs-lookup"><span data-stu-id="ee607-138">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="ee607-139">Передайте <xref:System.Exception> объект, обрабатываемый `try` - `catch` блоком.</span><span class="sxs-lookup"><span data-stu-id="ee607-139">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="ee607-140">Передайте текст сообщения как <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ee607-140">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="ee607-141">Установите одно из следующих значений для свойства <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee607-141">Set one of the following values for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span></span>  
  
    -   <span data-ttu-id="ee607-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore>— Отображает кнопки **прервать**, **повторить**и **пропустить** .</span><span class="sxs-lookup"><span data-stu-id="ee607-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore> - displays the **Abort**, **Retry**, and **Ignore** buttons.</span></span>  
  
    -   <span data-ttu-id="ee607-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> — отображает пользовательские кнопки.</span><span class="sxs-lookup"><span data-stu-id="ee607-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - displays custom buttons.</span></span>  
  
    -   <span data-ttu-id="ee607-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK>— Отображает кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="ee607-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK> - displays the **OK** button.</span></span>  
  
    -   <span data-ttu-id="ee607-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel>— Отображает кнопки **ОК** и **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="ee607-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel> - displays the **OK** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="ee607-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel>— Отображает кнопки **повторить** и **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="ee607-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel> - displays the **Retry** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="ee607-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo>— Отображает кнопки **Да** и **нет** .</span><span class="sxs-lookup"><span data-stu-id="ee607-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo> - displays **Yes** and **No** buttons.</span></span>  
  
    -   <span data-ttu-id="ee607-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel>— Отображает кнопки **Да**, **нет**и **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="ee607-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel> - displays **Yes**, **No**, and **Cancel** buttons.</span></span>  
  
5.  <span data-ttu-id="ee607-149">При использовании пользовательских кнопок вызовите один из перегруженных методов <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A>, чтобы указать текст для пользовательских кнопок, количество которых не более пяти (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ee607-149">(Optional) If you use custom buttons, call one of the overloads of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> method to specify text for up to five custom buttons.</span></span>  
  
6.  <span data-ttu-id="ee607-150">Вызовите метод <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="ee607-150">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="ee607-151">Передайте родительское окно, к которому относится окно сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-151">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="ee607-152">(Необязательно) Какую из кнопок нажал пользователь, можно определить, проверив значение возвращенного перечисления <xref:System.Windows.Forms.DialogResult>.</span><span class="sxs-lookup"><span data-stu-id="ee607-152">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span> <span data-ttu-id="ee607-153">При использовании пользовательских кнопок отметьте значение объекта <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> для свойства <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A>, чтобы определить, какую пользовательскую кнопку нажал пользователь.</span><span class="sxs-lookup"><span data-stu-id="ee607-153">If you use custom buttons, note the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> for the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> property to determine which of the custom buttons the user clicked.</span></span>  
  
#### <a name="to-allow-users-to-decide-whether-to-show-the-exception-message-box"></a><span data-ttu-id="ee607-154">Как разрешить пользователям показывать или не показывать окно сообщения об исключении</span><span class="sxs-lookup"><span data-stu-id="ee607-154">To allow users to decide whether to show the exception message box</span></span>  
  
1.  <span data-ttu-id="ee607-155">Добавьте в проект управляемого кода ссылку на сборку Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="ee607-155">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="ee607-156">Используемых Добавьте `using` директиву (C#) или `Imports` (Visual Basic .NET) для использования <xref:Microsoft.SqlServer.MessageBox> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ee607-156">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="ee607-157">Создайте экземпляр класса <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> одним из двух следующих способов.</span><span class="sxs-lookup"><span data-stu-id="ee607-157">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="ee607-158">Передайте <xref:System.Exception> объект, обрабатываемый `try` - `catch` блоком.</span><span class="sxs-lookup"><span data-stu-id="ee607-158">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="ee607-159">Передайте текст сообщения как <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ee607-159">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="ee607-160">Задайте для свойства <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ee607-160">Set the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="ee607-161">Укажите текст с вопросом пользователю, показывать ли снова окно сообщения об исключении, для свойства <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="ee607-161">(Optional) Specify the text that asks the user to decide whether to show the exception message box again for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span></span> <span data-ttu-id="ee607-162">По умолчанию используется текст «Не показывать больше это сообщение».</span><span class="sxs-lookup"><span data-stu-id="ee607-162">The default text is "Do not show this message again."</span></span>  
  
6.  <span data-ttu-id="ee607-163">Если требуется сохранять принятое пользователем решение лишь на протяжении выполнения приложения, присвойте значение свойства <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> глобальной переменной <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="ee607-163">If you need to keep the user's decision only for the duration of the application's execution, set the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> to a global <xref:System.Boolean> variable.</span></span> <span data-ttu-id="ee607-164">Вычислите это значение перед созданием экземпляра окна сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-164">Evaluate this value before creating an instance of the exception message box.</span></span>  
  
7.  <span data-ttu-id="ee607-165">Если необходимо постоянно хранить принятое пользователем решение, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="ee607-165">If you need to store a user's decision permanently, do the following:</span></span>  
  
    1.  <span data-ttu-id="ee607-166">Вызовите метод CreateSubKey, чтобы открыть используемый вашим приложением пользовательский раздел реестра, и задайте значение <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A>, равное возвращаемому объекту.</span><span class="sxs-lookup"><span data-stu-id="ee607-166">Call the CreateSubKey method to open a custom registry key that your application uses, and set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> to the returned RegistryKey object.</span></span>  
  
    2.  <span data-ttu-id="ee607-167">Установите в свойстве <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> имя используемого значения реестра.</span><span class="sxs-lookup"><span data-stu-id="ee607-167">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> to the name of the registry value that is used.</span></span>  
  
    3.  <span data-ttu-id="ee607-168">Задайте для параметра <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ee607-168">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> to `true`.</span></span>  
  
    4.  <span data-ttu-id="ee607-169">Вызовите метод <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="ee607-169">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="ee607-170">Вычисляется указанный раздел реестра, и окно сообщения об исключении отображается только тогда, когда хранящиеся в разделе реестра данные равны 0.</span><span class="sxs-lookup"><span data-stu-id="ee607-170">The specified registry key is evaluated, and the exception message box is displayed only if the data stored in the registry key is 0.</span></span> <span data-ttu-id="ee607-171">Если же отображается диалоговое окно и пользователь устанавливает флажок до нажатия кнопки, то данным в разделе реестра присваивается 1.</span><span class="sxs-lookup"><span data-stu-id="ee607-171">If the dialog box is displayed and the user selects the check box before clicking a button, the data in the registry key is set to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee607-172">Пример</span><span class="sxs-lookup"><span data-stu-id="ee607-172">Example</span></span>  
 <span data-ttu-id="ee607-173">В этом примере используется окно сообщения об исключении только с кнопкой **ОК** , чтобы отобразить сведения из исключения приложения, которые включают в себя обрабатываемое исключение и дополнительную информацию, отражающую специфику данного приложения.</span><span class="sxs-lookup"><span data-stu-id="ee607-173">This example uses the exception message box with only the **OK** button to display information from an application exception that includes the handled exception along with additional application-specific information.</span></span>  
  
 [!code-csharp[HowTo#emb_showOKbutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showokbutton)]  
  
 [!code-vb[HowTo#emb_vb_showOKbutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showokbutton)]  
  
## <a name="example"></a><span data-ttu-id="ee607-174">Пример</span><span class="sxs-lookup"><span data-stu-id="ee607-174">Example</span></span>  
 <span data-ttu-id="ee607-175">В этом примере используется окно сообщения об исключении с кнопками **Да** и **Нет** , одну из которых выбирает пользователь.</span><span class="sxs-lookup"><span data-stu-id="ee607-175">This example uses the exception message box with **Yes** and **No** buttons from which the user chooses.</span></span>  
  
 [!code-csharp[HowTo#emb_showYesNobutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showyesnobutton)]  
  
 [!code-vb[HowTo#emb_vb_showYesNobutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showyesnobutton)]  
  
## <a name="example"></a><span data-ttu-id="ee607-176">Пример</span><span class="sxs-lookup"><span data-stu-id="ee607-176">Example</span></span>  
 <span data-ttu-id="ee607-177">В этом примере используется окно сообщения об исключении с пользовательскими кнопками.</span><span class="sxs-lookup"><span data-stu-id="ee607-177">This example uses the exception message box with custom buttons.</span></span>  
  
 [!code-csharp[HowTo#emb_showcustombutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showcustombutton)]  
  
 [!code-vb[HowTo#emb_vb_showcustombutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showcustombutton)]  
  
## <a name="example"></a><span data-ttu-id="ee607-178">Пример</span><span class="sxs-lookup"><span data-stu-id="ee607-178">Example</span></span>  
 <span data-ttu-id="ee607-179">В этом примере используется флажок для определения того, показывать ли окно сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-179">This example uses the check box to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_usecheckbox](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_usecheckbox)]  
  
 [!code-vb[HowTo#emb_vb_usecheckbox](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_usecheckbox)]  
  
## <a name="example"></a><span data-ttu-id="ee607-180">Пример</span><span class="sxs-lookup"><span data-stu-id="ee607-180">Example</span></span>  
 <span data-ttu-id="ee607-181">В этом примере используется флажок и раздел реестра для определения того, показывать ли окно сообщения об исключении.</span><span class="sxs-lookup"><span data-stu-id="ee607-181">This example uses the check box and a registry key to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_useregkey](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_useregkey)]  
  
 [!code-vb[HowTo#emb_vb_useregkey](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_useregkey)]  
  
## <a name="example"></a><span data-ttu-id="ee607-182">Пример</span><span class="sxs-lookup"><span data-stu-id="ee607-182">Example</span></span>  
 <span data-ttu-id="ee607-183">В этом примере используется окно сообщения об исключении для отображения дополнительных сведений, полезных при диагностике и устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="ee607-183">This example uses the exception message box to show additional information that is helpful when troubleshooting or debugging.</span></span>  
  
 [!code-csharp[HowTo#emb_moreinfo](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_moreinfo)]  
  
 [!code-vb[HowTo#emb_vb_moreinfo](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_moreinfo)]  
  
  
