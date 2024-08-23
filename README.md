# SenseTalk_Introduction

I decided to start this Introduction series based on what I learned from what I read. It provided me with a good opportunity to practice and review, and I thought we could create a more explanatory document for those who come after us, so I started this work. I began working on this documentation over the weekend. 

Right now, I’ve tried to provide some very basic syntax information, based on what I’ve learned about SenseTalk so far. I hope this will serve as a good introductory document for people who have no prior knowledge of SenseTalk. I will continue to add more content here. 

Additionally, I created an ultra-basic, simple version in HTML format. If you want, you can also access the site version through the GitHub link below. We can develop this further together later on.


👽 👾 https://hakanovski.github.io/SenseTalk_Introduction/main.html 👾 👽


Please feel free to contribute and add your knowledge as well. 

That’s all for now.

H A ❌ A N





// 1. Google Chrome'u Açın
DoubleClick "GoogleChrome_DesktopIcon"  // Masaüstündeki Chrome ikonuna çift tıklayın
WaitFor 10, "ChromeOpenedImage"  // Chrome'un tamamen açılmasını bekleyin

// 2. Adres Çubuğuna Tıklayın ve Yeni URL'yi Girin
Click "va_insider_url"  // Chrome'un adres çubuğuna tıklayın
TypeText "https://www1.dfhost.com/va-fsc-gov/Default.aspx?menu=RegressionTestPage", Return  // Yeni URL'yi girin ve Enter'a basın

// 3. VAPIVCard ile Giriş Yapın
Click "SignInWithVAPIVCard"  // Giriş yap butonuna tıklayın
WaitFor 10, "OK_Certificate_Info"  // Authentication için bekleyin
Click {Image:"OK_Certificate_Info", WaitFor:10}  // Sertifika onay butonuna tıklayın

// 4. PIN Kodu Sorma Durumunu Kontrol Et ve Giriş Yap
// PIN kodu istenip istenmediğini kontrol etmek için bir bekleme döngüsü
put 0 into attemptCounter
repeat until ImageFound("PIN_Login_Agility") or attemptCounter is 3
    if ImageFound("PIN_Login_Agility") then
        log "PIN prompt detected. Entering PIN."
        TypeText "270607", Enter  // PIN kodunu girin ve Enter'a basın
        exit repeat
    else
        wait 5  // Bekle ve tekrar kontrol et
        add 1 to attemptCounter
    end if
end repeat

if attemptCounter is 3 then
    log "PIN prompt was not found after several attempts. Proceeding without PIN entry."
end if

// 5. Ekstra Kontroller ve İşlemler
// Burada ek işlemleri devam ettirebilirsiniz
