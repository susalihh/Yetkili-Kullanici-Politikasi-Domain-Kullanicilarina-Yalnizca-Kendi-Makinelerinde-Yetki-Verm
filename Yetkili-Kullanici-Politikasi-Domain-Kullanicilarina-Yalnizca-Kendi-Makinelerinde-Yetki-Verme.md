# Yetkili Kullanıcı Politikası, Domain Kullanıcılarına Yalnızca Kendi Makinelerinde Yetki Verme #
Kullanıcılara kendi makinelerinde yetki verilmesi 2 şekilde yapılabilir.
## 1- Her kullanıcının yalnızca kendi makinesinde tam yetki verilmesi

Liman MYS arayüzünden politikalar arayüzüne gidilir;
 **Liman MYS'de Domain Eklentisindeki LDAP OU'sundan politika oluşturulan OU seçilir ve Obje Türünden Politikalara tıklanır**

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f2ocde4qcqnvlotqqe7o.png)

Politikalar listesinden ilgili politikası tıklanır;

Açılan pencerede "Makine" seçilir ve "Tümü" üzerine tıklanıp Yetkili Kullanıcı seçilir.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tmag7kkwojdrsmejo1ns.png)

Kullanıcı Ekle bölümünde;

1. KULLANICI ADI, domainde oluşturulmuş kullanıcı adı girilir,
2. HOSTNAME KISITLAMASI, yetkinin verileceği makine/makineler seçilir,
3. SONA ERME TARİHİ, yetkinin sona erme tarihi girilir. Boş bırakıldığında politikanın etkisi hiçbir zaman bitmez.

Girilen veriler sonrasında;

kullanici1 adlı kullanıcının sadece "cl01" adlı makinede ve kullanici2 adlı kullanıcının sadece "cl02" adlı makinede tam yetkiye sahip olacaktır. Aynı işlem kullanıcı yerine gruba vermek istenilirse "Grup Ekle" bölümüne gidilip GRUP ADI kısmına domainde oluşturulmuş grup adı ve HOSTNAME KISITLAMASI kısmınıda yetkinin verileceği makine/makineler girilir.

## 2- Her kullanıcının yalnızca kendi makinesinde kısıtlı komut çalıştırabilmesi

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dhw80le8xiicidhq77cn.png)

Yetkili Kullanıcıdan Komut için izin ver bölümünde;

1. KULLANICI ADI, domainde oluşturulmuş kullanıcı adı girilir,
2. GRUP ADI, domainde oluşturulmuş grup adı girilir,
3. KOMUT, izin verilecek komut girilir,
4. BU KOMUTU PAROLASIZ ÇALIŞTIRMAYA İZİN VER, isteğe göre komutu parolasız çalıştırma izni verilir,
5. HOSTNAME KISITLAMASI, izin verilen komutun hangi makine/makinelerde uygulanacağı seçilir,
6. SONA ERME TARİHİ, yetkinin sona erme tarihi girilir. Boş bırakıldığında politikanın etkisi hiçbir zaman bitmez.

Girilen veriler sonrasında;

"kullanici1" adlı kullanıcı sadece "cl01" adlı makinede **'*' ile eşleşen php modüllerini** yükleme yetkisine sahip olacaktır. **'*' olmadığında komutun birebir aynı yazılması gerekir.** Aynı işlem kullanıcı yerine gruba vermek istenilirse aynı bölümündeki KULLANICI ADI yerine GRUP ADI kısmına domainde oluşturulmuş grup adı girilir.
