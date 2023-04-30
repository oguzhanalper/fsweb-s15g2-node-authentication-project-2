# JSON Web Tokenlerini Kullanma

## Giriş

JSON Web Tokenlerini kullanarak kimlik doğrulama ve yetkilendirme içeren bir API oluşturmak için `Node.js`, `Express` ve `Knex` kullanın.

## Talimatlar

### Görev 1: Proje Kurulumu

Fokrlayın, clone'layın ve bolca commitleyin.

### Görev 2: MVP

Aşağıdaki görevleri tamamlamak ve uygulamanın tüm testleri geçmesi için gereken kodları yazacak ve gerekli paketleri yükleyeceksiniz.

#### 2A - Veritabanı Erişim Fonksiyonları

Erişim fonksiyonlarını `api/users/users-model.js` dosyasına yazacaksınız:

- [+] `bul`
- [+] `goreBul`
- [+] `idyeGoreBul`

#### 2B - Middleware Fonksiyonları

Auth middlewarelarını `api/auth/auth-middleware.js` dosyasına yazacaksınız:

- [+] `sinirli`
- [+] `sadece`
- [+] `usernameVarmi`
- [+] `rolAdiGecerlimi`

#### 2C - Uçnoktalar

Kimlik doğrulama, JSON Web Tokenler kullanılarak uygulanacaktır.

Aşağıdaki uçnoktaları `api/auth/auth-router.js` dosyasına yazın:

- [ ] `[POST] /api/auth/register`
- [ ] `[POST] /api/auth/login`

`api/users/users-router.js` içindeki uçnoktalar hazır ama yine de bir göz atın:

- [ ] `[GET] /api/users` - sadece geçerli tokena sahip olan kullanıcılar erişebilir
- [ ] `[GET] /api/users/:user_id` - sadece geçerli tokena sahip olan kullanıcılar ve rolü admin olan kullanıcılar erişebilir

#### 2D - Secret Dosyaları

`secrets/index.js` dosyasını tamamlayın.

#### Users Şeması

| bölüm    | veri tipi        | metadata                                      |
| :------- | :--------------- | :-------------------------------------------- |
| user_id  | unsigned integer | primary key, auto-increments, generated by db |
| username | string           | required, unique                              |
| password | string           | required                                      |
| role_id  | unsigned integer | foreign key, required                         |

#### Roles Şeması

| bölüm     | veri tipi        | metadata                                      |
| :-------- | :--------------- | :-------------------------------------------- |
| role_id   | unsigned integer | primary key, auto-increments, generated by db |
| role_name | string           | required, unique                              |

#### Notlar

- Testler için `npm test`.
- Proje `migrate`, `rollback` ve `seed` scriptleriyle beraber gelmektedir. veritabanını resetleyebilirsiniz.
- Ek dosyalar oluşturabilirsiniz ancak **mevcut dosyaları veya klasörleri taşımayın veya yeniden adlandırmayın**.
- Fazladan kitaplıklar kurmak veya fazladan betik eklemek dışında `package.json` dosyanızı değiştirmeyin. Mevcut kitaplıkları güncellemeyin.
- Çözümünüzde, en iyi uygulamaları izlemeniz ve temiz ve profesyonel sonuçlar üretmeniz çok önemlidir.
- Çalışmanızı gözden geçirmek, iyileştirmek ve değerlendirmek için zaman planlayın.
- Çalışmanızda yazım denetimi ve dilbilgisi denetimi de dahil olmak üzere temel profesyonel cilalama işlemleri gerçekleştirin.

### Görev 3: Esnek Görevler

- Kaydolmak, oturum açmak ve kullanıcı listesini görüntülemek için bir React uygulaması oluşturun. React becerilerinizi geliştirmeye devam etmelisiniz.
