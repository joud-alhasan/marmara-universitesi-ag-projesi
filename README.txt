İÇİNDEKİLER

    Giriş

    Yöntem

    Bulgular

    GitHub

GİRİŞ

Bu projede, Marmara Üniversitesi’nin ağ altyapısı Cisco Packet Tracer yazılımı kullanılarak modellenmiş ve simüle edilmiştir. Seçilen bazı kampüs ve fakültelerin, birbirleriyle güvenli ve hızlı şekilde haberleşmesini sağlayacak bir ağ yapısı tasarlanmıştır.

Projenin temel hedefleri şunlardır:

    Gerçek bir üniversite altyapısını temel alarak ağ topolojisi oluşturmak,

    DHCP, Email, FTP, DNS ve HTTP sunucularının işleyişini gözlemlemek,

    Statik yönlendirme, VLAN, güvenlik duvarı ve sunucu yapılandırmaları gibi temel ağ bileşenlerini öğrenmek ve uygulamak.

YÖNTEM

Kullanılan Yazılım:

    Cisco Packet Tracer

Yapılan Çalışmalar:
1. Topoloji Planlaması

Göztepe, Maltepe ve Başıbüyük kampüsleri örnek olarak seçilmiştir. Yıldız topolojisine uygun olarak Göztepe Kampüsü merkez olarak yapılandırılmış, diğer kampüsler bu merkeze bağlanmıştır. Sunucular Göztepe Kampüsü'nde toplanmıştır.

Her kampüs için örnek fakülteler ve kütüphaneler belirlenmiştir.

    Her kampüse: 1 router ve 1 switch

    Her fakülteye: 1 switch

    Fakültelerdeki laboratuvar ve kütüphaneler için: VLAN yapılandırmaları yapılmıştır.

Göztepe Kampüsü’nün dış ağ bağlantısı bir router üzerinden sağlanmış ve bu bağlantıya güvenlik amaçlı bir Firewall eklenmiştir. Güvenilir ve güvenilmez ağlar simüle edilerek gerekli güvenlik konfigürasyonları gerçekleştirilmiştir.
2. Kullanılan Cihazlar

    6 Router (3 kampüs + 3 dış ağ simülasyonu)

    11 Switch (3 kampüs + 6 fakülte + 2 dış ağ)

    7 Sunucu (DHCP, Email, FTP, DNS, 3 adet HTTP)

    18 Host cihaz

3. IP Planlaması

    Her bölüm için farklı alt ağlar (subnet) belirlendi.

    Router’larda arayüzler IP ile konfigüre edilerek ağlar tanımlandı.

    Switch’lerde VLAN’lar oluşturuldu.

4. Sunucu Yapılandırmaları

DHCP Server:

    Alt ağlara ait IP havuzları tanımlandı.

    Router'larda ip helper-address komutu kullanılarak farklı ağlardan gelen DHCP istekleri yönlendirildi.

Email Server:

    Domain tanımlandı, kullanıcılar oluşturuldu ve e-posta gönderimi/alımları test edildi.

FTP Server:

    Dosya aktarımı için kullanıcı tanımlandı ve izinler verildi.

DNS Server:

    HTTP sunucuların domain/IP eşlemeleri yapıldı.

    Host cihazlarda DNS konfigürasyonları tamamlandı.

HTTP Server:

    Üniversiteye ait web sayfaları bu sunucularda barındırıldı.

    DNS kayıtları üzerinden erişim test edildi.

5. Yönlendirme

    Statik yönlendirme protokolü uygulanarak ağlar arası iletişim sağlandı.

6. VLAN Yapılandırması

    Fakültelerde laboratuvar ve kütüphane VLAN’ları oluşturuldu.

    Router arayüzlerinde bu VLAN’lara ilişkin IP tanımlamaları yapıldı.

7. İnternet Simülasyonu

    Güvenli ve güvensiz olmak üzere iki ayrı dış ağ oluşturuldu.

    Firewall, bu ağlardan gelen trafiği filtrelemek üzere yapılandırıldı.

BULGULAR
Genel Topoloji

Topoloji yıldız şeklinde yapılandırılmıştır. Göztepe Kampüsü merkez olarak belirlenmiş ve diğer kampüsler buraya bağlanmıştır. Bu merkezileşme sayesinde, veri trafiği ve sunucu yönetimi daha etkin hale getirilmiştir.

Göztepe Kampüsü aynı zamanda dış ağ bağlantı noktasını da temsil eder. Firewall ile dış ağdan gelen trafiğin kontrolü sağlanmıştır. Bu sayede:

    Üniversite içindeki cihazların dış sunuculara (HTTP, DNS, Email) erişimi,

    Dış kaynaklardan gelen erişimlerin filtrelenmesi,

    Gerçek bir üniversite altyapısına benzer güvenli ve merkezi bir yapı oluşturulmuştur.

Göztepe Kampüsü

Göztepe Kampüsü'nde konumlandırılan sunucular:

    DHCP Server: VLAN’lardaki host cihazlara otomatik IP ataması.

    DNS Server: Domain-IP dönüşümü.

    Email Server: E-posta sistemi ve kullanıcı tanımlamaları.

    FTP Server: Dosya aktarımı işlemleri.

    HTTP Server: Web sayfalarına alan adıyla erişim.

Ayrıca dış ağ bağlantısı bu kampüs üzerinden sağlanmış, Firewall konfigürasyonu ile güvenli trafik yönetimi gerçekleştirilmiştir.
Maltepe Kampüsü

Maltepe Kampüsü'nde Teknoloji ve Mühendislik fakülteleri için farklı VLAN’lar yapılandırılmıştır. Laboratuvarlar da kendi VLAN’larına ayrılmıştır. Bu segmentasyon, kampüs içi veri trafiğini izole ederek güvenlik ve yönetimi artırmıştır.
Başıbüyük Kampüsü

Başıbüyük Kampüsü’nde Tıp Fakültesi ve Kütüphane birimleri için VLAN’lar oluşturulmuştur. Bu VLAN’lar sayesinde cihazlar arasında güvenli ve yönetilebilir bir yapı sağlanmıştır.
İnternet

İnternet simülasyonunda iki dış ağ tasarlanmıştır:

    Güvenli Ağ (Trusted Network)

    Güvensiz Ağ (Untrusted Network)

Göztepe Kampüsü üzerinden gelen trafiğe, Firewall cihazı aracılığıyla güvenlik katmanı uygulanmıştır.

    Güvenli ağdan gelen veriler kabul edilmiştir.

    Güvensiz ağdan gelen bağlantılar ise engellenmiştir.

Bu sayede dış dünya ile olan bağlantılarda kontrollü ve güvenli iletişim sağlanmıştır.
