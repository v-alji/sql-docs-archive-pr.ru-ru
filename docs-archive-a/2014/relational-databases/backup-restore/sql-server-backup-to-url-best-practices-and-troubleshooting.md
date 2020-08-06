---
title: Резервное копирование в SQL Server по URL-адресу — рекомендации и устранение неполадок | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665391"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a>Резервное копирование SQL Server на URL-адрес — рекомендации и устранение неполадок
  В этом разделе рассматриваются рекомендации и советы по устранению неполадок с SQL Server при создании резервных копий и восстановлении с помощью службы BLOB-объектов Azure.  
  
 Дополнительную сведения об использовании службы хранилища BLOB-объектов Azure для операций резервного копирования или восстановления SQL Server см. в разделах:  
  
-   [Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [Руководство. Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a>Управление резервными копиями  
 В следующем списке перечислены общие рекомендации по управлению резервным копированием.  
  
-   Рекомендуется присваивать каждому файлу уникальное имя, чтобы предотвратить случайное перезаписывание больших двоичных объектов.  
  
-   При создании контейнера рекомендуется установить уровень доступа **private**, чтобы большие двоичные объекты в контейнере могли читать или записывать только те пользователи или учетные записи, которые предоставили необходимую информацию для проверки подлинности.  
  
-   Для SQL Server баз данных на экземпляре SQL Server, работающем на виртуальной машине Azure, используйте учетную запись хранения в том же регионе, что и виртуальная машина, чтобы избежать затрат на передачу данных между регионами. Использование одного региона также обеспечивает оптимальную производительность операций резервного копирования и восстановления.  
  
-   Сбой во время резервного копирования может привести к созданию неработоспособного файла резервной копии. Рекомендуется периодически проводить поиск неудачных резервных копий и удалять файлы больших двоичных объектов. Дополнительные сведения см. в разделе [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).  
  
-   Использование параметра `WITH COMPRESSION` во время резервного копирования может уменьшить стоимость хранения и транзакционные издержки хранения. Также может сократиться время, необходимое для выполнения резервного копирования.  
  
## <a name="handling-large-files"></a>Обработка больших файлов  
  
-   Операция резервного копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется в несколько потоков, чтобы оптимизировать передачу данных к службам хранилищ BLOB-объектов Azure.  Однако производительность зависит от различных факторов, в том числе от пропускной способности ISV и размера базы данных. Если планируется создавать резервные копии больших баз данных или файловых групп в локальной базе данных SQL Server, вначале рекомендуется проверить пропускную способность. [Соглашение об уровне обслуживания службы хранилища Azure](https://go.microsoft.com/fwlink/?LinkId=271619) имеет максимальную продолжительность обработки больших двоичных объектов, которые можно принять во внимание.  
  
-   При создании резервных копий больших файлов очень важно использовать параметр `WITH COMPRESSION` в соответствии с рекомендациями, приведенными в разделе **Управление резервным копированием**.  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a>Устранение неполадок при резервном копирование или восстановлении по URL-адресу  
 Ниже приведено несколько простых способов устранения неполадок при создании резервной копии или восстановлении из службы хранилища BLOB-объектов Azure.  
  
 Чтобы избежать ошибок из-за неподдерживаемых параметров или ограничений, ознакомьтесь со списком ограничений и поддержкой команд резервного копирования и восстановления в статье [SQL Server резервное копирование и восстановление с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .  
  
 **Ошибки проверки подлинности:**  
  
-   УЧЕТные данные — это новый параметр, который требуется для резервного копирования или восстановления из службы хранилища BLOB-объектов Azure. Ниже приводятся возможные ошибки, связанные с учетными данными.  
  
     Учетные данные, заданные в команде `BACKUP` или `RESTORE`, не существуют. Чтобы избежать этой проблемы, можно включить инструкцию T-SQL для создания учетных данных, если она отсутствует в инструкции резервного копирования. Ниже приводится пример, который можно использовать.  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   Учетные данные существуют, но учетная запись, которая используется для запуска команды резервного копирования, не имеет разрешения доступа к учетным данным. Используйте учетную запись для входа в роль **db_backupoperator** с разрешением **Изменение любых учетных данных** .  
  
-   Проверьте имя учетной записи хранилища и значение ключа. Информация, которая хранится в учетных данных, должна соответствовать значениям свойств учетной записи хранения Azure, используемым в операциях резервного копирования и восстановления.  
  
 **Ошибки и сбои резервного копирования:**  
  
-   Параллельное выполнение резервного копирования в один большой двоичный объект вызывает сбой одной из резервных копий с ошибкой **Ошибка инициализации** .  
  
-   Используйте следующие журналы об ошибке, чтобы помочь при устранении неполадок в резервных ошибках:  
  
    -   Установите флаг трассировки 3051, чтобы включить ведение записей в конкретном журнале ошибок в следующем формате:  
  
         BackupToUrl- \<instname> - \<dbname> -Action- \<PID> . log \<action> , где является одним из следующих:  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   Можно также найти сведения, просмотрев журнал событий Windows в разделе Журналы приложений с именем "Sqlbackuptourl»".  
  
-   При восстановлении из сжатой резервной копии может появиться следующее сообщение об ошибке:  
  
    -   **Произошла SqlException 3284. Серьезность: 16 состояние: 5**  
        **Сообщение метка файла на устройстве " https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak " не согласовано. Повторите инструкцию Reissue с тем же размером блока, который использовался для создания резервного набора данных: "65536" похоже на возможное значение.**  
  
         Чтобы устранить эту ошибку, перезапустите инструкцию `BACKUP` с помощью заметки `BLOCKSIZE = 65536`.  
  
-   Ошибка во время резервного копирования из-за больших двоичных объектов с активной арендой: сбой операции резервного копирования может привести к созданию больших двоичных объектов с активными арендами.  
  
     Если эта инструкция резервного копирования повторяется, то операция резервного копирования может завершиться со следующей ошибкой:  
  
     **Резервное копирование на URL-адрес получило исключение из удаленной конечной точки. Сообщение об исключении: удаленный сервер возвратил ошибку: (412) в настоящее время существует аренда для большого двоичного объекта, однако для запроса не указан идентификатор аренды**.  
  
     Если инструкция восстановления выполнялись в резервном файле большого двоичного объекта с активной арендой, операция резервного копирования может завершиться со следующей ошибкой:  
  
     **Сообщение об исключении: удаленный сервер вернул ошибку: (409) конфликт…**  
  
     Если возникает такая ошибка, файлы больших двоичных объектов следует удалить. Дополнительные сведения об этом сценарии и устранении этой проблемы см. в разделе [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).  
  
## <a name="proxy-errors"></a>Ошибки прокси-сервера  
 При использовании прокси-серверов для доступа к Интернету возможны следующие проблемы.  
  
 **Регулирование соединений прокси-серверами.**  
  
 Прокси-серверы могут иметь параметры, ограничивающие количество соединений в минуту. Процесс резервного копирования на URL-адрес является многопоточным, в связи с чем заданное ограничение может быть превышено. В этом случае прокси-сервер разрывает соединение. Чтобы устранить эту проблему, измените параметры прокси-сервера таким образом, чтобы SQL Server его не использовал.   Далее приведено несколько примеров типов или сообщений об ошибках, которые можно встретить в журнале ошибок.  
  
-   Ошибка записи в " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ": резервное копирование на URL-адрес получило исключение от удаленной конечной точки. Сообщение об исключении: не удалось прочитать данные из транспортного соединения. Соединение было закрыто.  
  
-   В файле "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" произошла неустранимая ошибка ввода-вывода "Не удалось получить ошибку из удаленной конечной точки".  
  
     Сообщение 3013, уровень 16, состояние 1, строка 2  
  
     Процесс BACKUP DATABASE завершается аварийно.  
  
-   Баккупиорекуест:: Репортиоеррор: Ошибка записи на устройстве резервного копирования " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ". Ошибка операционной системы. Процесс резервного копирования на URL-адрес получил исключение от удаленной конечной точки. Сообщение об исключении: не удалось прочитать данные из транспортного соединения. Соединение было закрыто.  
  
 Если включить подробный уровень ведения журнала с помощью флага трассировки 3051, то в журналы также может быть занесено следующее сообщение.  
  
 Код состояния HTTP 502, ошибка прокси-сервера сообщения о состоянии HTTP (количество HTTP-запросов в минуту превышает установленный предел. Обратитесь к администратору сервера ISA.  )  
  
 **Параметры прокси-сервера по умолчанию не используются.**  
  
 Иногда параметры по умолчанию не вызывают ошибки проверки подлинности прокси-сервера, как показано ниже:*произошла неустранимая ошибка ввода-вывода в файле " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: " резервная копия на URL-адрес получил исключение от удаленной конечной точки. Сообщение об исключении: удаленный сервер вернул ошибку: (407)* **требуется проверка подлинности прокси-сервера**.  
  
 Чтобы устранить эту проблему, создайте файл конфигурации, позволяющий процессу резервного копирования по URL-адресу использовать параметры прокси-сервера по умолчанию. Для этого выполните следующие действия.  
  
1.  Создайте файл конфигурации BackuptoURL.exe.config со следующим XML-кодом:  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  Поместите файл конфигурации в папку Binn на экземпляре SQL Server. Например, если мой SQL Server установлен на диске C компьютера, разместите файл конфигурации здесь: *C:\Program FILES\MICROSOFT SQL Server\MSSQL12. \<InstanceName> \MSSQL\Binn*.  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a>Устранение неполадок с управляемым резервным копированием SQL Server в Azure  
 Так как служба управляемого резервного копирования SQL Server использует операцию копирования на URL-адрес, советы по устранению проблемы, описанные в предыдущих подразделах, относятся к базам данных и экземплярам, использующим данную службу.  Сведения об устранении неполадок SQL Server управляемой архивации в Azure подробно описаны в [статье Устранение неполадок SQL Server управляемой архивации в Azure](sql-server-managed-backup-to-microsoft-azure.md).  
  
## <a name="see-also"></a>См. также:  
 [Восстановление из резервных копий, хранящихся в Azure](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  