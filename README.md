# GoKurulum

Merhabalar, bugün bilgisayarımı sıfırladım ve geliştirme araçlarımın hepsini baştan kuruyorum, bu doğrultuda kurulum aşamasınıda özetleyen bir şeyler karalamak istedim. Kısacası, kimsenin zerre kadar ilgilenmeyeceği bir yazı yazmaya karar verdim, bu yazımda Go kurulumunun ardından doğru GOROOT ve GOPATH değişkenlerinin ayarlanması ve 3. parti paketleri kurmak, projeyi ayağa kaldırmak için neler yaptım, bunları aktaracağım.
Ben yazımı MacOS için yazıyorum, diğer UNIX dağıtımlarında da benzer konfigürasyonlarla çözülebileceğini düşünüyorum.
Öncelikle bu adresten Go’yu indirdim.
Ardından paketi kurdum, next, next, next (en sevdiğim)
Paket kurulumu ile birlikte Go PATH’inize ekleniyor, yani kontrol etmek için komut satırına
# go version
yazabilirsiniz.
Şimdi ise GOROOT ve GOPATH ortam değişkenleri için değerler atamalıyız.
Bu değişkenler hakkında kısaca bilgi vermekte fayda var, GOROOT, Go’nun kurulu olduğu dizine ulaşmak için kullanılıyor.
MacOS için bu değer /usr/local/go olmalı.
Bu değerin doğru olup olmadığını kontrol etmek için
# which go
komutu ile Go’nun nerede kurulu olduğunu öğrenebilirsiniz.
Sonuç olarak bana şu şekilde bir yanıt geldi;
# /usr/local/go/bin/go
Bu yanıta istinaden executable yani çalıştırılabilir Go dosyasının hangi dizinde olduğunu öğrenmiş oldum.
Bir sorun gözükmüyor, artık GOROOT değerine
# /usr/local/go
olarak atama yapabilirim, bunun için profile dosyamı açıyorum,
# nano $HOME/.bash_profile
İçerisine şu satırı giriyorum.
# export GOROOT=/usr/local/go
Evet, şimdi ise Go projelerini barındıracağım bir dizine ihtiyacım var, bu dizinde benim oluşturacağım veya klonlayacağım Go projeleri olacak ayrıca yine bu dizin içerisinde indirmiş olduğum 3. parti paketler barınacak.
Bunun için masaüstüne bir dizin açacağım, bunu siz kendi isteğinize göre düzenleyebilirsiniz. Ben masaüstüne kurmayı tercih ediyorum.
# cd /Users/furkan/Desktop/
# mkdir GoProjects
# cd GoProjects
# mkdir src;mkdir pkg
Bu komutlar doğrultusunda masaüstüne GoProjects adında bir klasör oluşturdum ve içerisine src ve pkg adında 2 klasör daha oluşturdum.
Şu an GOPATH yani Go projelerimin ve 3. parti paketlerin barınacağı klasörüm hazır.
Go’nun paketlere erişmesi için PATH’e eklemek gerekiyor bunun tekrar profile dosyamı açıyorum;
# nano $HOME/.bash_profile
şu satırı ekliyorum;
# export GOPATH=/Users/furkan/Desktop/GoProjects
Evet, Go kurulumu ve ortam değişkenleride tamamlandı, bu yazı doğrultusunda kendi tarafımda go get ile indirdiğim paketler ve kendi paketlerim doğru şekilde çalışıyor.
Değişkenlerimizin kalıcı hale gelebilmesi için ise;
# source $HOME/.bash_profile
komutunu giriyoruz.

# mod ve sum için.

go mod init main.go

go mod tidy
