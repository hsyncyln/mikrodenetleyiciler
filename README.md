# mikrodenetleyiciler

ADCON1=7

TRISB=%11110000
TRISD=%00000000

sayi var byte
sayi2 var byte
sonuc var byte
islem var word





portd=0

etiket:

    portb.0=1
    portb.1=0
    portb.2=0
    portb.3=0
    if portb.0=1 then
       
        if portb.4=1  then
            sayi=7
            portd=sayi
            pause 10
        endif
         if portb.5=1  then
            sayi=8
            portd=sayi
            pause 10
        endif
         if portb.6=1  then
            sayi=9
            portd=sayi
            pause 10
        endif
        if portb.7=1  then
            islem="/"
            sayi2=sayi
            pause 10
        endif
        
      
    endif
    
    
    pause 10
    
    portb.0=0
    portb.1=1
    portb.2=0
    portb.3=0
    
    
    if portb.1=1 then
       
        if portb.4=1  then
            sayi=4
            portd=sayi
            pause 10
        endif
         if portb.5=1  then
            sayi=5
            portd=sayi
            pause 10
        endif
         if portb.6=1  then
            sayi=6
            portd=sayi
            pause 10
        endif
         if portb.7=1  then
            islem="*"
            sayi2=sayi
            pause 10
        endif
      
    endif
    
    pause 10
    
    portb.0=0
    portb.1=0
    portb.2=1
    portb.3=0
    if portb.2=1 then
       
        if portb.4=1  then
            sayi=1
            portd=sayi
            pause 10
        endif
         if portb.5=1  then
            sayi=2
            portd=sayi
            pause 10
        endif
         if portb.6=1  then
            sayi=3
            portd=sayi
            pause 10
        endif
         if portb.7=1  then
            islem="-"
            sayi2=sayi
            pause 10
        endif
      
    endif
    
     pause 10
     
    portb.0=0
    portb.1=0
    portb.2=0
    portb.3=1
    if portb.3=1 then
       
       
         if portb.5=1  then
            sayi=0
            portd=sayi
            pause 10
        endif
         if portb.6=1  then
            
            if islem="/"  then
                sonuc=sayi2/sayi
                if sonuc>=10 then
                    sonuc=sonuc+6
                endif
                portd=sonuc
                pause 10
            endif
            
            if islem="+"  then
                sonuc=sayi2+sayi
                if sonuc>=10 then
                    sonuc=sonuc+6
                endif
                portd=sonuc
                pause 10
            endif
            
            if islem="-"  then
                sonuc=sayi2-sayi
                if sonuc>=10 then
                    sonuc=sonuc+6
                endif
                portd=sonuc
                pause 10
            endif
            if islem="*"  then
                sonuc=sayi2*sayi
                if sonuc>=10 then
                    sonuc=sonuc+6
                endif
                portd=sonuc
                pause 10
            endif
            
            
            
            
        endif
         if portb.7=1  then
            islem="+"
            sayi2=sayi
            pause 10
        endif
      
    endif
    
    
    
goto etiket

