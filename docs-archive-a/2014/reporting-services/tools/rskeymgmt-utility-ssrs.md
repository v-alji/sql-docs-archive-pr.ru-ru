---
title: Программа rskeymgmt (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], encryption
- joining report server instances [SQL Server]
- report server scale-out deployments [Reporting Services]
- cryptography [Reporting Services]
- multiple report server instances
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], scale-out deployments
- encryption [Reporting Services]
- rskeymgmt utility
- scale-out deployments [Reporting Services]
ms.assetid: 53f1318d-bd2d-4c08-b19f-c8b698b5b3d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae4bdd6656cf5b29f8fd40fcf730f49a6de8f32e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735989"
---
# <a name="rskeymgmt-utility-ssrs"></a><span data-ttu-id="1b228-102">Программа rskeymgmt (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1b228-102">rskeymgmt Utility (SSRS)</span></span>
  <span data-ttu-id="1b228-103">Извлекает, восстанавливает, создает и удаляет симметричный ключ, используемый для защиты важных данных сервера отчетов от несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="1b228-103">Extracts, restores, creates, and deletes the symmetric key used to protect sensitive report server data against unauthorized access.</span></span> <span data-ttu-id="1b228-104">Эта программа также используется для соединения экземпляров сервера отчетов в конфигурацию с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-104">This utility is also used to join report server instances in a scale-out deployment.</span></span> <span data-ttu-id="1b228-105">*Конфигурация сервера отчетов с масштабным развертыванием* означает множество экземпляров сервера отчетов, которые совместно используют одну базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-105">A *report server scale-out deployment* refers to multiple report server instances that share a single report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b228-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b228-106">Syntax</span></span>  
  
```  
  
      rskeymgmt {-?}  
{-eextract}  
{-aapply}  
{-ddeleteall}  
{-srecreatekey}  
{-rremoveinstancekey}  
{-jjoinfarm}  
{-iinstance}  
{-ffile}  
{-pencryptionpassword}  
{-mremotecomputer}  
{-ninstancenameofremotecomputer}  
{-uadministratoruseraccount}  
{-vadministratorpassword}  
{-ttrace}  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b228-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1b228-107">Arguments</span></span>  
 <span data-ttu-id="1b228-108">**-?**</span><span class="sxs-lookup"><span data-stu-id="1b228-108">**-?**</span></span>  
 <span data-ttu-id="1b228-109">Показывает синтаксис аргументов **rskeymgmt** .</span><span class="sxs-lookup"><span data-stu-id="1b228-109">Displays the syntax of **rskeymgmt** arguments.</span></span>  
  
 <span data-ttu-id="1b228-110">**-e**</span><span class="sxs-lookup"><span data-stu-id="1b228-110">**-e**</span></span>  
 <span data-ttu-id="1b228-111">Извлекает симметричный ключ, используемый для шифрования и расшифровки данных для экземпляра сервера отчетов, чтобы его можно было скопировать в файл.</span><span class="sxs-lookup"><span data-stu-id="1b228-111">Extracts the symmetric key used to encrypt and decrypt data for the report server instance so that you can copy it to a file.</span></span>  
  
 <span data-ttu-id="1b228-112">Этот аргумент не принимает значения.</span><span class="sxs-lookup"><span data-stu-id="1b228-112">This argument does not take a value.</span></span> <span data-ttu-id="1b228-113">Однако, чтобы закончить извлечение, в командную строку необходимо включить дополнительные аргументы.</span><span class="sxs-lookup"><span data-stu-id="1b228-113">However, you must include additional arguments on the command line to complete the extraction.</span></span> <span data-ttu-id="1b228-114">Это аргументы `-f` и `-p`.</span><span class="sxs-lookup"><span data-stu-id="1b228-114">The arguments that you must specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="1b228-115">**-a**</span><span class="sxs-lookup"><span data-stu-id="1b228-115">**-a**</span></span>  
 <span data-ttu-id="1b228-116">Заменяет существующий симметричный ключ копией, содержащейся в файле резервной копии, защищенном паролем.</span><span class="sxs-lookup"><span data-stu-id="1b228-116">Replaces an existing symmetric key with a copy that you provide in a password protected backup file.</span></span> <span data-ttu-id="1b228-117">Обновляются все экземпляры симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="1b228-117">All instances of the symmetric key are updated.</span></span>  
  
 <span data-ttu-id="1b228-118">Этот аргумент не принимает значения.</span><span class="sxs-lookup"><span data-stu-id="1b228-118">This argument does not take a value.</span></span> <span data-ttu-id="1b228-119">Однако, чтобы выбрать файл, содержащий ключ, который будет применен, в командную строку необходимо включить дополнительные аргументы.</span><span class="sxs-lookup"><span data-stu-id="1b228-119">However, you must include additional arguments on the command line to select the file that contains the key to be applied.</span></span> <span data-ttu-id="1b228-120">Аргументы, которые можно указать, включают `-f` и `-p`.</span><span class="sxs-lookup"><span data-stu-id="1b228-120">The arguments that you can specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="1b228-121">**-d**</span><span class="sxs-lookup"><span data-stu-id="1b228-121">**-d**</span></span>  
 <span data-ttu-id="1b228-122">Удаляет все экземпляры симметричного ключа и все зашифрованные данные в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-122">Deletes all symmetric key instances and all encrypted data in a report server database.</span></span> <span data-ttu-id="1b228-123">Этот аргумент не принимает значения.</span><span class="sxs-lookup"><span data-stu-id="1b228-123">This argument does not take a value.</span></span>  
  
 `-s`  
 <span data-ttu-id="1b228-124">Формирует новый симметричный ключ и повторно шифрует все зашифрованное содержимое с его помощью.</span><span class="sxs-lookup"><span data-stu-id="1b228-124">Generates a new symmetric key and re-encrypts all encrypted content using the new key.</span></span> <span data-ttu-id="1b228-125">Повторно создаются все экземпляры симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="1b228-125">All instances of the symmetric key are regenerated.</span></span>  
  
 `-j`  
 <span data-ttu-id="1b228-126">Настраивает удаленный экземпляр сервера отчетов для совместного использования базы данных сервера отчетов, которая используется локальным экземпляром сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-126">Configures a remote report server instance to share the report server database that is used by the local report server instance.</span></span>  
  
 <span data-ttu-id="1b228-127">**-r**  *installationID*</span><span class="sxs-lookup"><span data-stu-id="1b228-127">**-r**  *installationID*</span></span>  
 <span data-ttu-id="1b228-128">Удаляет сведения о симметричном ключе для указанного экземпляра сервера отчетов, удаляя таким образом сервер отчетов из конфигурации с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-128">Removes the symmetric key information for a specific report server instance, thereby removing the report server from a scale-out deployment.</span></span> <span data-ttu-id="1b228-129">Идентификатор *installationID* — это значение идентификатора GUID, которое находится в файле RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="1b228-129">The *installationID* is a GUID value that can be found in the RSReportserver.config file.</span></span>  
  
 <span data-ttu-id="1b228-130">`-f`  *file*</span><span class="sxs-lookup"><span data-stu-id="1b228-130">`-f`  *file*</span></span>  
 <span data-ttu-id="1b228-131">Указывает полный путь к файлу, в котором хранится резервная копия симметричных ключей.</span><span class="sxs-lookup"><span data-stu-id="1b228-131">Specifies a fully qualified path to the file that stores a backup copy of the symmetric keys.</span></span>  
  
 <span data-ttu-id="1b228-132">Для **rskeymgmt -e**в указанный файл записывается симметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="1b228-132">For **rskeymgmt -e**, the symmetric key is written to the file you specify.</span></span>  
  
 <span data-ttu-id="1b228-133">Для **rskeymgmt -a**значение симметричного ключа, которое хранится в файле, применяется к экземпляру сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-133">For **rskeymgmt -a**, the symmetric key value stored in the file is applied to the report server instance.</span></span>  
  
 <span data-ttu-id="1b228-134">`-p`  *пароль*</span><span class="sxs-lookup"><span data-stu-id="1b228-134">`-p`  *password*</span></span>  
 <span data-ttu-id="1b228-135">(Необходим для `-f`.) Определяет пароль, используемый для создания резервной копии или применения симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="1b228-135">(Required for `-f`) Specifies the password used to back up or apply a symmetric key.</span></span> <span data-ttu-id="1b228-136">Это значение не может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="1b228-136">This value cannot be empty.</span></span>  
  
 `-i`  
 <span data-ttu-id="1b228-137">Определяет локальный экземпляр сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-137">Specifies a local report server instance.</span></span> <span data-ttu-id="1b228-138">Этот аргумент необязателен, если сервер отчетов установлен на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию (значение по умолчанию для аргумента `-i` — MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="1b228-138">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-i` is MSSQLSERVER).</span></span> <span data-ttu-id="1b228-139">Если сервер отчетов установлен как именованный экземпляр, аргумент `-i` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="1b228-139">If you installed the report server as a named instance, `-i` is required.</span></span>  
  
 `-m`  
 <span data-ttu-id="1b228-140">Указывает имя удаленного компьютера, на котором размещается экземпляр сервера отчетов, присоединяемый к конфигурации сервера отчетов с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-140">Specifies the name of the remote computer that hosts the report server instance you are joining to the report server scale-out deployment.</span></span> <span data-ttu-id="1b228-141">Используйте имя компьютера, которое идентифицирует его в сети.</span><span class="sxs-lookup"><span data-stu-id="1b228-141">Use the name of the computer that identifies it on your network.</span></span>  
  
 `-n`  
 <span data-ttu-id="1b228-142">Указывает имя экземпляра сервера отчетов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1b228-142">Specifies the name of the report server instance on a remote computer.</span></span> <span data-ttu-id="1b228-143">Этот аргумент необязателен, если сервер отчетов установлен на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию (значение по умолчанию для аргумента `-n` — MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="1b228-143">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-n` is MSSQLSERVER).</span></span> <span data-ttu-id="1b228-144">Если сервер отчетов установлен как именованный экземпляр, аргумент `-n` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="1b228-144">If you installed the report server as a named instance, `-n` is required.</span></span>  
  
 <span data-ttu-id="1b228-145">`-u`  *UserAccount*</span><span class="sxs-lookup"><span data-stu-id="1b228-145">`-u`  *useraccount*</span></span>  
 <span data-ttu-id="1b228-146">Указывает учетную запись администратора на удаленном компьютере, который присоединяется к масштабному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1b228-146">Specifies the administrator account on the remote computer that you are joining to the scale-out deployment.</span></span> <span data-ttu-id="1b228-147">Если учетная запись не указана, используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b228-147">If an account is not specified, the credentials of the current user are used.</span></span>  
  
 <span data-ttu-id="1b228-148">`-v`  *пароль*</span><span class="sxs-lookup"><span data-stu-id="1b228-148">`-v`  *password*</span></span>  
 <span data-ttu-id="1b228-149">(Необходим для `-u`.) Указывает пароль учетной записи администратора на удаленном компьютере, который присоединяется к конфигурации с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-149">(Required for `-u`) Specifies the password of an administrator account on the remote computer that you want to join to the scale-out deployment.</span></span>  
  
 <span data-ttu-id="1b228-150">**-t**  *Трассировка*</span><span class="sxs-lookup"><span data-stu-id="1b228-150">**-t**  *trace*</span></span>  
 <span data-ttu-id="1b228-151">Выводит сообщения об ошибках в журнал трассировки.</span><span class="sxs-lookup"><span data-stu-id="1b228-151">Outputs error messages to the trace log.</span></span> <span data-ttu-id="1b228-152">Этот аргумент не принимает значения.</span><span class="sxs-lookup"><span data-stu-id="1b228-152">This argument does not take a value.</span></span> <span data-ttu-id="1b228-153">Дополнительные сведения см. в статье [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="1b228-153">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="1b228-154">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1b228-154">Permissions</span></span>  
 <span data-ttu-id="1b228-155">Для запуска этого средства необходимо быть локальным администратором. Запускать его необходимо локально на компьютере, где размещается сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-155">You must be a local administrator to run the tool, and you must run it locally on the computer that hosts the report server.</span></span> <span data-ttu-id="1b228-156">Программа rskeymgmt работает с локальным экземпляром сервера отчетов Windows (программа не может подключиться к удаленным экземплярам службы сервера отчетов Windows, и поэтому она не может использоваться для управления ключами шифрования удаленного экземпляра сервера отчетов).</span><span class="sxs-lookup"><span data-stu-id="1b228-156">The rskeymgmt utility works with the local Report Server Windows instance (the utility cannot connect to remote instances of the Report Server Windows service so it cannot be used to manage the encryption keys of a remote report server instance).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b228-157">При использовании аргументов `-u` и `-v` убедитесь, что указана учетная запись, которая имеет разрешения администратора на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1b228-157">If you are using the `-u` and `-v` arguments, be sure to specify an account that has administrator permissions on the remote computer.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1b228-158">Примеры</span><span class="sxs-lookup"><span data-stu-id="1b228-158">Examples</span></span>  
 <span data-ttu-id="1b228-159">В следующих примерах показаны способы использования **rskeymgmt**.</span><span class="sxs-lookup"><span data-stu-id="1b228-159">The following examples illustrate ways of using **rskeymgmt**.</span></span> <span data-ttu-id="1b228-160">Также показано, как извлечь, восстановить и удалить ключи шифрования и как настроить конфигурацию сервера отчетов с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-160">The following examples show how to extract, restore, and delete encryption keys, and how to configure a report server scale-out deployment.</span></span>  
  
#### <a name="extracting-encryption-keys"></a><span data-ttu-id="1b228-161">Извлечение ключей шифрования</span><span class="sxs-lookup"><span data-stu-id="1b228-161">Extracting Encryption Keys</span></span>  
 <span data-ttu-id="1b228-162">В этом примере показано, как создать резервную копию ключа шифрования и сохранить ее в защищенном паролем файле на гибком диске.</span><span class="sxs-lookup"><span data-stu-id="1b228-162">This example shows how to create a backup copy of the encryption key and save it to a password-protected file on a floppy disk.</span></span> <span data-ttu-id="1b228-163">Если сервер отчетов установлен на именованный экземпляр, добавьте аргумент `-i`.</span><span class="sxs-lookup"><span data-stu-id="1b228-163">If the report server is installed as a named instance, add the `-i` argument.</span></span>  
  
```  
rskeymgmt -e -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="restoring-encryption-keys"></a><span data-ttu-id="1b228-164">Восстановление ключей шифрования из копии</span><span class="sxs-lookup"><span data-stu-id="1b228-164">Restoring Encryption Keys</span></span>  
 <span data-ttu-id="1b228-165">В этом примере показано, как заменить ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="1b228-165">This example shows how to replace the encryption key.</span></span> <span data-ttu-id="1b228-166">Необходимо указать местоположение резервной копии ключа и пароль, который разблокирует файл.</span><span class="sxs-lookup"><span data-stu-id="1b228-166">You must specify the location of the backup copy of the key and the password that unlocks the file.</span></span>  
  
```  
rskeymgmt -a -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="deleting-encryption-keys-and-encrypted-content"></a><span data-ttu-id="1b228-167">Удаление ключей шифрования и зашифрованного содержимого</span><span class="sxs-lookup"><span data-stu-id="1b228-167">Deleting Encryption Keys and Encrypted Content</span></span>  
 <span data-ttu-id="1b228-168">В этом примере показано, как удалить все ключи шифрования, сохраненные на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-168">This example shows how to delete all encryption keys stored in a report server.</span></span> <span data-ttu-id="1b228-169">Если сервер отчетов установлен в конфигурации с масштабным развертыванием, то будут удалены ключи шифрования для всех экземпляров сервера отчетов, включенных в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1b228-169">If your installation is a report server scale-out deployment, the encryption keys for all report server instances that are included in the deployment will be deleted.</span></span> <span data-ttu-id="1b228-170">При удалении ключа шифрования удаляются также все зашифрованные значения, существующие в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-170">Deleting an encryption key also deletes any existing encrypted values in the report server database.</span></span> <span data-ttu-id="1b228-171">Дополнительные сведения о зашифрованном содержимом см. в разделе [Хранение зашифрованных данных сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span><span class="sxs-lookup"><span data-stu-id="1b228-171">For more information about encrypted content, see [Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span></span>  
  
```  
rskeymgmt -d  
```  
  
#### <a name="joining-a-remote-report-server-named-instance-to-a-scale-out-deployment"></a><span data-ttu-id="1b228-172">Присоединение удаленного именованного экземпляра сервера отчетов к конфигурации с масштабным развертыванием</span><span class="sxs-lookup"><span data-stu-id="1b228-172">Joining a Remote Report Server Named Instance to a Scale-out Deployment</span></span>  
 <span data-ttu-id="1b228-173">В этом примере показано, как добавить экземпляр сервера отчетов, установленный на удаленном компьютере, к конфигурации сервера отчетов с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-173">This example shows how to add a report server instance that is installed on a remote computer to a report server scale-out deployment.</span></span> <span data-ttu-id="1b228-174">Эту команду необходимо запустить на одном из компьютеров, который уже настроен на использование общей базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b228-174">You must run the command on one of the computers that is already configured to use the shared database.</span></span> <span data-ttu-id="1b228-175">Аргументы команды указывают удаленный экземпляр сервера отчетов, который нужно присоединить к конфигурации с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-175">The command arguments specify the remote report server instance you want to join to the scale-out deployment.</span></span>  
  
```  
rskeymgmt -j -m <remotecomputer> -n <namedreportserverinstance> -u <administratoraccount> -v <administratorpassword>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1b228-176">Конфигурация сервера отчетов с масштабным развертыванием означает модель развертывания, где несколько экземпляров сервера отчетов совместно используют одну базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-176">A report server scale-out deployment refers to a deployment model where multiple report server instances share the same report server database.</span></span> <span data-ttu-id="1b228-177">База данных сервера отчетов может использоваться любым экземпляром сервера отчетов, который хранит в ней свои симметричные ключи.</span><span class="sxs-lookup"><span data-stu-id="1b228-177">A report server database can be used by any report server instance that stores its symmetric keys in the database.</span></span> <span data-ttu-id="1b228-178">Например, если база данных сервера отчетов содержит сведения о ключах для трех экземпляров сервера отчетов, все три экземпляра считаются элементами одной конфигурации с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-178">For example, if a report server database contains key information for three report server instances, all three instances are considered to members of the same scale-out deployment.</span></span>  
  
#### <a name="joining-report-server-instances-on-the-same-computer"></a><span data-ttu-id="1b228-179">Объединение экземпляров сервера отчетов на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="1b228-179">Joining Report Server Instances on the Same Computer</span></span>  
 <span data-ttu-id="1b228-180">Можно создать конфигурацию с масштабным развертыванием из нескольких экземпляров сервера отчетов, установленных на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1b228-180">You can create a scale-out deployment from multiple report server instances that are installed on the same computer.</span></span> <span data-ttu-id="1b228-181">При объединении экземпляров сервера отчетов, установленных локально, нельзя использовать аргументы `-u` и `-v`.</span><span class="sxs-lookup"><span data-stu-id="1b228-181">Do not set the `-u` and `-v` arguments if you are joining report server instances that are installed locally.</span></span> <span data-ttu-id="1b228-182">Аргументы `-u` и `-v` используются только при подсоединении экземпляра с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="1b228-182">The `-u` and `-v` arguments are used only when you are joining an instance from a remote computer.</span></span> <span data-ttu-id="1b228-183">Если задать аргументы, появится такая ошибка: "Учетные данные пользователя не могут использоваться для локальных подключений".</span><span class="sxs-lookup"><span data-stu-id="1b228-183">If you specify the arguments, you will get the following error: "User credentials cannot be used for local connections."</span></span>  
  
 <span data-ttu-id="1b228-184">Следующий пример показывает синтаксис для создания масштабного развертывания из нескольких локальных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="1b228-184">The following example illustrates the syntax for creating a scale-out deployment using multiple local instances.</span></span> <span data-ttu-id="1b228-185">В этом примере <`initializedinstance`> — имя экземпляра, который уже инициализирован для использования базы данных сервера отчетов, а <`newinstance`> — имя экземпляра, который необходимо добавить в развертывание:</span><span class="sxs-lookup"><span data-stu-id="1b228-185">In this example, <`initializedinstance`> is the name of an instance that is already initialized to use the report server database, and <`newinstance`> is the name of the instance that you want to add to the deployment:</span></span>  
  
```  
rskeymgmt -j -i <initializedinstance> -m <computer name> -n <newinstance>  
```  
  
#### <a name="removing-encryption-keys-for-a-single-report-server-in-a-scale-out-deployment"></a><span data-ttu-id="1b228-186">Удаление ключей шифрования отдельного сервера отчетов в конфигурации с масштабным развертыванием</span><span class="sxs-lookup"><span data-stu-id="1b228-186">Removing Encryption Keys for a Single Report Server in a Scale-out Deployment</span></span>  
 <span data-ttu-id="1b228-187">В этом примере показано, как удалить ключи шифрования отдельного сервера отчетов в конфигурации с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-187">This example shows how to remove the encryption keys for a single report server in a report server scale-out deployment.</span></span> <span data-ttu-id="1b228-188">Ключи удаляются из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-188">The keys are removed from the report server database.</span></span> <span data-ttu-id="1b228-189">Как только ключи этого экземпляра сервера отчетов будут удалены, он больше не сможет обращаться к зашифрованным данным в базе данных и будет фактически удален из конфигурации с масштабным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="1b228-189">Once the keys for that report server instance are removed, that report server instance can no longer access encrypted data in the database, effectively removing it from the scale-out deployment.</span></span>  
  
 <span data-ttu-id="1b228-190">Чтобы удалить экземпляр сервера отчетов из масштабного развертывания, требуется указать идентификатор установки.</span><span class="sxs-lookup"><span data-stu-id="1b228-190">Removing a report server instance from a scale-out deployment requires you to specify an installation ID.</span></span> <span data-ttu-id="1b228-191">Идентификатор установки — это идентификатор GUID, сохраненный в файле RSReportserver.config экземпляра сервера отчетов, для которого планируется удалить ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="1b228-191">The installation ID is a GUID stored in the RSReportserver.config file of the report server instance for which you want to remove encryption keys.</span></span> <span data-ttu-id="1b228-192">На компьютере, который планируется удалить из конфигурации с масштабным развертыванием, необходимо выполнить следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1b228-192">You must run the following command on the computer that you want to remove from the scale-out deployment.</span></span> <span data-ttu-id="1b228-193">Если сервер отчетов установлен на именованный экземпляр, используйте аргумент `-i`, чтобы указать экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1b228-193">If the report server is installed as a named instance, use the `-i` argument to specify the instance.</span></span> <span data-ttu-id="1b228-194">Дополнительные сведения см. в статье [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="1b228-194">For more information, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>  
  
```  
rskeymgmt -r <installationID>  
```  
  
## <a name="file-location"></a><span data-ttu-id="1b228-195">Расположение файла</span><span class="sxs-lookup"><span data-stu-id="1b228-195">File Location</span></span>  
 <span data-ttu-id="1b228-196">Rskeymgmt.exe находится в папке \*\* \<*drive*> : \PROGRAM Files\Microsoft SQL Server\110\Tools\Binn\*\* или в \*\* \<*drive*> папке: \Program Files (x86) \Microsoft SQL Server\110\Tools\Binn\*\*.</span><span class="sxs-lookup"><span data-stu-id="1b228-196">Rskeymgmt.exe is located at **\<*drive*>:\Program Files\Microsoft SQL Server\110\Tools\Binn** or at **\<*drive*>:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="1b228-197">Программу можно запустить из любой папки файловой системы.</span><span class="sxs-lookup"><span data-stu-id="1b228-197">You can run the utility from any folder on your file system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b228-198">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b228-198">Remarks</span></span>  
 <span data-ttu-id="1b228-199">Сервер отчетов шифрует сохраненные учетные данные и сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="1b228-199">A report server encrypts stored credentials and connection information.</span></span> <span data-ttu-id="1b228-200">Для шифрования данных используются открытый ключ и симметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="1b228-200">A public key and a symmetric key are used to encrypt data.</span></span> <span data-ttu-id="1b228-201">Для запуска сервера отчетов в базе данных сервера отчетов должен находиться набор допустимых ключей.</span><span class="sxs-lookup"><span data-stu-id="1b228-201">A report server database must have valid keys in order for the report server to run.</span></span> <span data-ttu-id="1b228-202">Программу **rskeymgmt** можно использовать для создания резервных копий, удаления или восстановления ключей.</span><span class="sxs-lookup"><span data-stu-id="1b228-202">You can use **rskeymgmt** to back up, delete, or restore the keys.</span></span> <span data-ttu-id="1b228-203">Если ключи не могут быть восстановлены, это средство предоставляет возможность удаления зашифрованного содержимого, которое больше не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="1b228-203">If the keys cannot be restored, this tool provides a way to delete encrypted content that can no longer be used.</span></span>  
  
 <span data-ttu-id="1b228-204">Программа **rskeymgmt** используется для управления набором ключей, указанным во время установки или при инициализации.</span><span class="sxs-lookup"><span data-stu-id="1b228-204">The **rskeymgmt** utility is used to manage the key set that is defined during Setup or during initialization.</span></span> <span data-ttu-id="1b228-205">Она подключается к локальной службе Windows сервера отчетов через конечную точку удаленного вызова процедур (RPC).</span><span class="sxs-lookup"><span data-stu-id="1b228-205">It connects to the local Report Server Windows service through a Remote Procedure Call (RPC) endpoint.</span></span> <span data-ttu-id="1b228-206">Чтобы эта программа могла работать, должна быть запущена служба Windows сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1b228-206">The Report Server Windows service must be running in order for this utility to work.</span></span>  
  
 <span data-ttu-id="1b228-207">Дополнительные сведения о ключах шифрования см. в разделах [Настройка ключей шифрования и управление ими (диспетчер конфигурации служб SSRS)](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) и [Инициализация сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="1b228-207">For more information about the encryption keys, see [Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) and [Initialize a Report Server &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b228-208">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b228-208">See Also</span></span>  
 <span data-ttu-id="1b228-209">[Настройка масштабного развертывания сервера отчетов в собственном режиме &#40;службы SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="1b228-209">[Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span></span>  
 <span data-ttu-id="1b228-210">[Сервер отчетов служб Reporting Services (основной режим)](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="1b228-210">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="1b228-211">[Программы командной строки сервера отчетов &#40;службы SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1b228-211">[Report Server Command Prompt Utilities &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span></span>  
 [<span data-ttu-id="1b228-212">Настройка ключей шифрования и управление ими (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="1b228-212">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
  
  
