# Django-M-lakat-Sorulari
## Q1. Discuss the Django architecture.

Ans. The developer provides the Model, the view and the template then just maps it to a URL and Django does the magic to serve it to the user.
It follows the MTV (Model template view pattern).


# S1 Django mimarisini tartışın.

Ans. Geliştirici Modeli, görünümü ve şablonu sağlar ve ardından onu bir URL'ye eşler ve Django bunu kullanıcıya sunmak için sihri yapar.
MTV'yi (Model şablon görünümü deseni) takip eder.
<hr>
<hr>

## Q2. Explain how you can set up the Database in Django.

### Ans: You can use the command edit mysite/setting.py , it is a normal python module with module level representing Django settings.

### Django uses SQLite by default; it is easy for Django users as such it won’t require any other type of installation. 
### In the case your database choice is different that you have to the following keys in the DATABASE ‘default’ item to match your database connection settings.

Engines: you can change database by using ‘django.db.backends.sqlite3’ , ‘django.db.backeneds.mysql’, ‘django.db.backends.postgresql_psycopg2’,
‘django.db.backends.oracle’ and so on
Name: The name of your database. In the case if you are using SQLite as your database, in that case database will be a file on your computer, 
Name should be a full absolute path, including file name of that file.
If you are not choosing SQLite as your database then settings like Password, Host, User, etc. must be added.
Django uses SQLite as default database, it stores data as a single file in the filesystem. If you do have a database server—PostgreSQL, MySQL,
Oracle, MSSQL—and want to use it rather than SQLite, then use your database’s administration tools to create a new database for your Django project. 
Either way, with your (empty) database in place, all that remains is to tell Django how to use it. This is where your project’s settings.py file comes in.

We will add the following lines of code to the setting.py file:

DATABASES = {
     'default': {
          'ENGINE' : 'django.db.backends.sqlite3',
          'NAME' : os.path.join(BASE_DIR, 'db.sqlite3'),
     }
}
 
# S.2 Veritabanını Django'da nasıl kurabileceğinizi açıklayın.

Cevap: edit mysite/setting.py komutunu kullanabilirsiniz, bu, Django ayarlarını temsil eden modül seviyesine sahip normal bir python modülüdür.

Django varsayılan olarak SQLite kullanır; Django kullanıcıları için kolaydır, bu nedenle başka bir kurulum türü gerektirmez.
Veritabanı seçiminizin farklı olması durumunda, veritabanı bağlantı ayarlarınızla eşleşmesi için DATABASE 'varsayılan' öğesinde aşağıdaki anahtarları kullanmanız gerekir.

Motorlar: 'Django.db.backends.sqlite3', 'Django.db.backeneds.mysql', 'Django.db.backends.postgresql_psycopg2' kullanarak veritabanını değiştirebilirsiniz,
'Django.db.backends.oracle' vb.
Ad: Veritabanınızın adı. Veritabanınız olarak SQLite kullanıyorsanız, bu durumda veritabanı bilgisayarınızda bir dosya olacaktır,
Ad, o dosyanın dosya adı da dahil olmak üzere tam bir mutlak yol olmalıdır.
Veritabanınız olarak SQLite seçmiyorsanız, Şifre, Ana Bilgisayar, Kullanıcı vb. ayarların eklenmesi gerekir.
Django, SQLite'ı varsayılan veritabanı olarak kullanır, verileri dosya sisteminde tek bir dosya olarak depolar. Bir veritabanı sunucunuz varsa—PostgreSQL, MySQL,
Oracle, MSSQL—ve SQLite yerine onu kullanmak istiyorsanız, Django projeniz için yeni bir veritabanı oluşturmak için veritabanınızın yönetim araçlarını kullanın.
Her iki durumda da, (boş) veritabanınız yerindeyken, geriye kalan tek şey Django'ya onu nasıl kullanacağını söylemek. Projenizin settings.py dosyasının geldiği yer burasıdır.

Setting.py dosyasına aşağıdaki kod satırlarını ekleyeceğiz:

DATABASES = {
     'default': {
          'ENGINE' : 'django.db.backends.sqlite3',
          'NAME' : os.path.join(BASE_DIR, 'db.sqlite3'),
     }
}

<hr>
<hr>
## Q3. Give an example how you can write a VIEW in Django?

Ans: This is how we can use write a view in Django:

from django.http import HttpResponse
import datetime

def Current_datetime(request):
     now = datetime.datetime.now()
     html = "<html><body>It is now %s</body></html>" % now
     return HttpResponse(html)



Returns the current date and time, as an HTML document

# S3 Django'da nasıl GÖRÜNÜM yazabileceğinize dair bir örnek var mı?

- Cevap: Django'da bir görünüm yazmayı şu şekilde kullanabiliriz:
from django.http import HttpResponse
import datetime

def Current_datetime(request):
     now = datetime.datetime.now()
     html = "<html><body>It is now %s</body></html>" % now
     return HttpResponse(html)
     
- Geçerli tarih ve saati bir HTML belgesi olarak döndürür

<hr>
<hr>
## Q4.  Mention what the Django templates consists of.

Ans: The template is a simple text file.  It can create any text-based format like XML, CSV, HTML, etc. 
A template contains variables that get replaced with values when the template is evaluated and tags (% tag %) 
that controls the logic of the template.


# S4 Django şablonlarının nelerden oluştuğundan bahsedin.

Cevap: Şablon basit bir metin dosyasıdır. XML, CSV, HTML vb. gibi herhangi bir metin tabanlı formatı oluşturabilir.
Bir şablon, şablon değerlendirildiğinde değerlerle değiştirilen değişkenler ve etiketler (% etiket %) içerir.
bu şablonun mantığını kontrol eder.

<hr>
<hr>
## Q5. Explain the use of session in Django framework?

Ans: Django provides session that lets you store and retrieve data on a per-site-visitor basis.
Django abstracts the process of sending and receiving cookies, by placing a session ID cookie on the client side, 
and storing all the related data on the server side.
So the data itself is not stored client side. This is nice from a security perspective.

# S5 Django çerçevesinde oturum kullanımını açıklar mısınız?

Cevap: Django, her bir site ziyaretçisi temelinde veri depolamanıza ve almanıza izin veren oturum sağlar.
Django, istemci tarafına bir oturum kimliği tanımlama bilgisi yerleştirerek tanımlama bilgileri gönderme ve alma sürecini özetler,
ve ilgili tüm verilerin sunucu tarafında saklanması.
Yani verilerin kendisi istemci tarafında saklanmaz. Bu güvenlik açısından güzel.


<hr>
<hr>
## Q6. List out the inheritance styles in Django.

Ans: In Django, there is three possible inheritance styles.

i.   Abstract Base Classes: This style is used when you only wants parent’s class to hold information that you don’t want to type out for each child model.
ii.  Multi-table Inheritance: This style is used If you are sub-classing an existing model and need each model to have its own database table.
iii. Proxy models: You can use this model, If you only want to modify the Python level behavior of the model, without changing the model’s fields.


# S6 Django'daki kalıtım stillerini listeleyin.

Cevap: Django'da üç olası kalıtım stili vardır.

### i. Soyut Temel Sınıflar: Bu stil, yalnızca ebeveyn sınıfının her çocuk modeli için yazmak istemediğiniz bilgileri tutmasını istediğinizde kullanılır.
### ii. Çoklu Tablo Kalıtımı: Bu stil, mevcut bir modeli alt sınıflıyorsanız ve her modelin kendi veritabanı tablosuna sahip olması gerekiyorsa kullanılır.
### iii. Proxy modelleri: Modelin alanlarını değiştirmeden sadece modelin Python düzeyindeki davranışını değiştirmek istiyorsanız bu modeli kullanabilirsiniz.

<hr>
<hr>
## Q7. How will you define Django ?

Ans: Django is a web framework in python to develop a web application in python. Django is a free and open source web application framework, 
written in Python. Django makes easier to build better web applications quickly and with less code.

# S7 Django'yu nasıl tanımlayacaksınız?

Cevap: Django, python'da bir web uygulaması geliştirmek için python'da bir web çerçevesidir. Django, ücretsiz ve açık kaynaklı bir web uygulama çerçevesidir.
Python'da yazılmıştır. Django, daha hızlı ve daha az kodla daha iyi web uygulamaları oluşturmayı kolaylaştırır.

<hr>
<hr>
## Q8. Mention what are the features available in Django?

Ans: Features available in Django are-

Admin Interface (CRUD)
Templating
Form handling
Internationalization
Session, user management, role-based permissions
Object-relational mapping (ORM)
Testing Framework
Fantastic Documentation
Security features

# S8 Django'da bulunan özelliklerin neler olduğundan bahseder misiniz?

Cevap: Django'da bulunan özellikler şunlardır:

Admin Interface (CRUD)
Templating
Form handling
Internationalization
Session, user management, role-based permissions
Object-relational mapping (ORM)
Testing Framework
Fantastic Documentation
Security features

<hr>
<hr>
## Q9. Mention the architecture of Django architecture?

Ans: Django architecture consists of-

Models: It describes your database schema and your data structure
Views: It controls what a user sees, the view retrieves data from appropriate models and execute any calculation made to the data and pass it to the template
Templates: It determines how the user sees it. It describes how the data received from the views should be changed or formatted for display on the page
Controller: The Django framework and URL parsing

# S9 Django mimarisinin mimarisinden bahseder misiniz?

Cevap: Django mimarisi şunlardan oluşur-

Modeller: Veritabanı şemanızı ve veri yapınızı tanımlar.
Görünümler: Bir kullanıcının ne gördüğünü kontrol eder, görünüm uygun modellerden veri alır ve verilere yapılan herhangi bir hesaplamayı yapar ve şablona iletir.
Şablonlar: Kullanıcının onu nasıl gördüğünü belirler. Görünümlerden alınan verilerin sayfada görüntülenmek üzere nasıl değiştirileceğini veya biçimlendirileceğini açıklar.
Denetleyici: Django çerçevesi ve URL ayrıştırma

<hr>
<hr>
## Q10. Why Django should be used for web-development?

Ans: It allows you to divide code modules into logical groups to make it flexible to change
To ease the website administration, it provides auto-generated web admin
It provides pre-packaged API for common user tasks
It gives you template system to define HTML template for your web page to avoid code duplication
It enables you to define what URL be for a given function
It enables you to separate business logic from the HTML
Everything is in python

# S10 Web geliştirme için neden Django kullanılmalıdır?

Cevap: Değiştirmeyi esnek hale getirmek için kod modüllerini mantıksal gruplara ayırmanıza olanak tanır.
Web sitesi yönetimini kolaylaştırmak için otomatik olarak oluşturulan web yöneticisi sağlar
Ortak kullanıcı görevleri için önceden paketlenmiş API sağlar
Kod tekrarını önlemek için web sayfanız için HTML şablonu tanımlamanız için şablon sistemi sağlar.
Belirli bir işlev için hangi URL'nin olacağını tanımlamanızı sağlar.
İş mantığını HTML'den ayırmanızı sağlar.
Her şey python'da

<hr>
<hr>
## Q11. Explain how you can setup static files in Django?

Ans: There are three main things required to set up static files in Django

Set STATIC_ROOT in settings.py
run manage.py collectsatic
set up a Static Files entry on the PythonAnywhere web tab

# S11 Django'da statik dosyaları nasıl kurabileceğinizi açıklayın.

Cevap: Django'da statik dosyalar kurmak için gereken üç ana şey vardır.

Set STATIC_ROOT in settings.py
run manage.py collectsatic

PythonAnywhere web sekmesinde bir Statik Dosyalar girişi ayarlayın

<hr>
<hr>
## Q12. Explain how you can use file based sessions?

Ans: To use file based session you have to set the SESSION_ENGINE settings to “django.contrib.sessions.backends.file”


# S12 Dosya tabanlı oturumları nasıl kullanabileceğinizi açıklayın.

Cevap: Dosya tabanlı oturumu kullanmak için SESSION_ENGINE ayarlarını “django.contrib.sessions.backends.file” olarak ayarlamalısınız.

<hr>
<hr>
## Q13. Explain the migration in Django and how you can do in SQL?

Migration in Django is to make changes to your models like deleting a model, adding a field, etc. into your database schema.  
There are several commands you use to interact with migrations.

Migrate
Makemigrations
Sqlmigrate
To do the migration in SQL, you have to print the SQL statement for resetting sequences for a given app name.

django-admin.py sqlsequencreset

Use this command to generate SQL that will fix cases where a sequence is out sync with its automatically incremented field data.

# S13 Django'daki geçişi ve SQL'de nasıl yapabileceğinizi açıklayın.

Django'da geçiş, veritabanı şemanıza model silme, alan ekleme vb. gibi modellerinizde değişiklik yapmaktır.
Geçişlerle etkileşim kurmak için kullandığınız birkaç komut vardır.

Göç
Göçmenler
Sqlmigrate
SQL'de geçiş yapmak için, belirli bir uygulama adı için dizileri sıfırlamak için SQL deyimini yazdırmanız gerekir.

django-admin.py sqlsequencreset

Bir dizinin otomatik olarak artan alan verileriyle eşitlenmediği durumları düzeltecek SQL oluşturmak için bu komutu kullanın.


<hr>
<hr>
## Q14. Mention what command line can be used to load data into Django?

Ans: To load data into Django you have to use the command line Django-admin.py loaddata. 
The command line will searches the data and loads the contents of the named fixtures into the database.

# S14 Django'ya veri yüklemek için hangi komut satırının kullanılabileceğini söyleyin?

Cevap: Django'ya veri yüklemek için Django-admin.py loaddata komut satırını kullanmanız gerekir.
Komut satırı verileri arar ve adlandırılmış fikstürlerin içeriğini veritabanına yükler.


<hr>
<hr>
## Q15. Explain what does django-admin.py makemessages command is used for?

This command line executes over the entire source tree of the current directory and abstracts all the strings marked for translation.  
It makes a message file in the locale directory.

# S15 Django-admin.py makemessages komutunun ne için kullanıldığını açıklayın.

Bu komut satırı, geçerli dizinin tüm kaynak ağacı üzerinde yürütülür ve çeviri için işaretlenen tüm dizeleri özetler.
Yerel dizinde bir mesaj dosyası oluşturur.


<hr>
<hr>
## Q16. Mention what does the Django field class types?

Ans: Field class types determines -
The database column type
The default HTML widget to avail while rendering a form field
The minimal validation requirements used in Django admin and in automatically generated forms

# S16 Django alan sınıfının ne tür olduğundan bahseder misiniz?

Cevap: Alan sınıfı türleri şunları belirler -
Veritabanı sütun türü
Bir form alanı oluştururken yararlanılacak varsayılan HTML widget'ı
Django admin'de ve otomatik olarak oluşturulan formlarda kullanılan minimum doğrulama gereksinimleri



<hr>
<hr>
## Q17. What is the usage of middlewares in Django?

Ans:
Below are the usage of middlewares in Django-
•Session management
•Cross-site request forgery protection
•Use authentication
•Content Gzipping

# S17 Django'da ara katman yazılımlarının kullanımı nedir?

Cevap:
Aşağıda Django'da ara katman yazılımlarının kullanımı verilmiştir.
• Oturum yönetimi
• Siteler arası talepte sahtecilik koruması
• Kimlik doğrulamayı kullan
•İçerik Gzipleme



<hr>
<hr>
## Q18. What are the roles of receiver and sender in signals?

Ans: The roles of receiver and sender in signals are-
Receiver: It specifies the callback function which will be connected to the signal.
Sender: It specifies a particular sender to receive a signal from.

# S18 Sinyallerde alıcı ve göndericinin rolleri nelerdir?

Cevap: Sinyallerde alıcı ve göndericinin rolleri:
Alıcı: Sinyale bağlanacak olan geri arama fonksiyonunu belirtir.
Gönderici: Sinyalin alınacağı belirli bir göndericiyi belirtir.


## Q19. Is Django Stable?

Ans: Yes, Django is quite stable. Many companies like Disqus, Instagram, Pinterest, and Mozilla have been using Django for many years.

# S19 Django Kararlı mı?

Cevap: Evet, Django oldukça kararlıdır. Disqus, Instagram, Pinterest ve Mozilla gibi birçok şirket uzun yıllardır Django kullanıyor.


<hr>
<hr>
## Q20.  Mention Caching Strategies That You Know In Django?

Ans: Few caching strategies that are available in Django are as follows:-

File sytem caching
In-memory caching
Using Memcached
Database caching

# S20 Django'da Bildiğiniz Önbelleğe Alma Stratejilerinden Bahsedin mi?

Cevap: Django'da kullanılabilen birkaç önbelleğe alma stratejisi aşağıdaki gibidir:-

Dosya sistemi önbelleğe alma
Bellek içi önbelleğe alma
Memcached'i kullanma
Veritabanı önbelleğe alma


<hr>
<hr>
## Q21. Is Django a content management system (CMS)?

Ans: No, Django is not a CMS. Instead, it is a Web framework and a programming tool that makes you able to build websites.


# S21 Django bir içerik yönetim sistemi (CMS) midir?

Cevap: Hayır, Django bir CMS değildir. Bunun yerine, bir Web çerçevesi ve web siteleri oluşturmanızı sağlayan bir programlama aracıdır.




## Q22. What is the usage of Django-admin.py and manage.py?

Ans: Django-admin.py: It is a Django's command line utility for administrative tasks.

Manage.py: It is an automatically created file in each Django project. It is a thin wrapper around the Django-admin.py. It has the following usage:

It puts your project's package on sys.path.
It sets the DJANGO_SETTING_MODULE environment variable to points to your project's setting.py file.




# S22 Django-admin.py ve Manage.py'nin kullanımı nedir?

Cevap: Django-admin.py: İdari görevler için bir Django'nun komut satırı yardımcı programıdır.

Manage.py: Her Django projesinde otomatik olarak oluşturulan bir dosyadır. Django-admin.py'nin etrafındaki ince bir sarıcıdır. Aşağıdaki kullanıma sahiptir:

Projenizin paketini sys.path'e koyar.
DJANGO_SETTING_MODULE ortam değişkenini projenizin settings.py dosyasına işaret edecek şekilde ayarlar.

<hr>
<hr>
## Q23. What are the signals in Django?

Ans: Signals are pieces of code which contain information about what is happening. 
A dispatcher is used to sending the signals and listen for those signals.

# S23 Django'daki sinyaller nelerdir?

Cevap: Sinyaller, neler olduğu hakkında bilgi içeren kod parçalarıdır.
Sinyalleri göndermek ve bu sinyalleri dinlemek için bir gönderici kullanılır.



<hr>
<hr>
## Q24. What is the role of Cookie in Django?

Ans: A cookie is a small piece of information which is stored in the client browser. 
It is used to store user's data in a file permanently (or for the specified time).
Cookie has its expiry date and time and removes automatically when gets expire. Django provides built-in methods to set and fetch cookie.

The set_cookie() method is used to set a cookie and get() method is used to get the cookie.

The request.COOKIES['key'] array can also be used to get cookie values.

# S24 Cookie'nin Django'daki rolü nedir?

Cevap: Çerez, istemci tarayıcısında saklanan küçük bir bilgi parçasıdır.
Kullanıcı verilerini kalıcı olarak (veya belirtilen süre boyunca) bir dosyada saklamak için kullanılır.
Çerezin son kullanma tarihi ve saati vardır ve süresi dolduğunda otomatik olarak kaldırılır. Django, tanımlama bilgisi ayarlamak ve getirmek için yerleşik yöntemler sağlar.

Bir çerez ayarlamak için set_cookie() yöntemi, çerezi almak için get() yöntemi kullanılır.

request.COOKIES['key'] dizisi, tanımlama bilgisi değerlerini almak için de kullanılabilir.
