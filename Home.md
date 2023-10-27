```
import random
import pyperclip

def başla():
    kelime = "m r t ğ ü n j k q r a s ö ç ö ü a s c v b ç i k q i z w k q ı o w e m y c v j f t h e b u ı o m r ü a s c x p n h l b n j u d f g e w ş m r t  w e b d"
    özel_karakter = "/ + . - * , _ - * & ! + . \ ? - % /  %  \ . ? - % , / + . _ ? \ ? - *  & ! + . /  - + - % ? +. - * - \ % / _ , % , - \ - ,"
    sayı = "8 0 2 8 4 6 3 5 9 0 5 7 1 7 4 6 3 5 9 0 2 8 9 5 0 1 7 6 4 7 4 3 8 3 2 0 5 9 1 2 6 9 0 2 8 1 5 9 3 5 1 9 5 3 2 3 8 0 2 8 2 0 9 5 1 7 4 2 8 4 8 1 6 1 9 9 2"
    

    büyük_kelime = kelime.upper() 
    kelime = kelime.split() 
    özel_karakter = özel_karakter.split()
    sayı = sayı.split() 
    ters_kelime = kelime[::-1] 
    şifre = [] 
    for i in range(10):  
        try:
            rastgele = random.randint(1,80) 
            şifre.append(kelime[rastgele]+özel_karakter[rastgele]+ters_kelime[rastgele]+sayı[rastgele]+büyük_kelime[rastgele])
        except:
            pass
    global a 
    a = ""
    for q in range(len(şifre)):
        a += str(şifre[q]).replace(" ","") 
        
başla() 
if len(a) < 10: 
    başla()
else: 
    try:
        seçenek = int(input("kopyalamak için 1'e basın\n")) 
        if seçenek == 1:
            pyperclip.copy(a)
            kayıt = input("bu şifre hangi site için\n") 
            with open(r"txt path","a") as dosya: 
                dosya.write(f"{kayıt} : {a}\n\n") 
    except:
        pass
    

```