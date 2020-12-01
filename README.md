# projek_akhir_apd

import datetime
from platform import uname_result

x = datetime.datetime.now()
print (x)

time = int (x.strftime("%H"))

if time >=00 and time  <= 10 :
    print ("_________________________")
    print ("       SELAMAT PAGI     ")
    print ("_________________________")
elif time >= 10 and  time <= 13  :
    print ("_________________________")
    print ("      SELAMAT SIANG      ")
    print ("_________________________")
elif time >= 13 and  time <= 18  :
    print ("_________________________")
    print ("       SELAMAT SORE      ")
    print ("_________________________")
elif time >= 18 and time  <= 24 :
    print ("_________________________")
    print ("      SELAMAT MALAM      ")
    print ("_________________________")
    print("\n")

Menu_Akun = {"username":{0:"ikhwan",1:"sultan",2:"fara",},
            "password":{0:2009106078,1:2009106095,2:2009106061,},
            "uang":{0:1000000000000,1:50000000000,2:25000000000,},
            "voucher":{0:12345678900000000000,1:12345678900000000000,2:12345678900000000000,},
            "harga":{0:{560000},1:{720000},2:{680000},},}

kepunyaan = {0:{},1:{},2:{},3:{},4:{}}
Dftrbrg = {"barang":{0:"laptop ASUS ROG GX800VH",1:"laptop MSI GT83VR 6RF TITAN",2:"laptop ASUS ROG Zephyrus Duo 15",},}

#fungsi
def Fungsi_admin():
    print("Hai Admin... \nMau liat apa nih")
    data_admin = int(input("\n1.liat data\n2.Tambah Data Barang\n3.Kembali ke Menu Utama\n4.Keluar\n>>> "))

    if data_admin == 1:

        data_admin = int(input("\n1.Data username\n2.Data password\n3.Data Uang\n4.Data Voucher\n5.Keluar\n>>> "))
        if data_admin == 1:
    
            print("INI LIST USERNAMENYA :")
            for i in range(0,len(Menu_Akun["username"])):           
                print(f"{i}.",Menu_Akun["username"][i])

            input()
            
        elif data_admin == 2:
    
            print("INI LIST PASSWORDNYA :")
            for i in range(0,len(Menu_Akun["password"])):
                
                print(f"{i}.",Menu_Akun["password"][i])        
            input()
                    
        
        elif data_admin == 3:
    
            print("INI LIST UANGNYA :")
            for i in range(0,len(Menu_Akun["uang"])):
                
                print(f"{i}. Rp.{Menu_Akun['uang'][i]}")        
            input()
      
        elif data_admin == 4:
    
            print("INI LIST VOUCHERNYA :")
            for i in range(0,len(Menu_Akun["voucher"])):
                
                print(f"{i}. Rp.{Menu_Akun['voucher'][i]}")        
            input()
           
     
        elif data_admin == 5:
            quit()
        Fungsi_admin()
         
    elif data_admin == 2:
       
        data_admin = int(input("\n1.Masukan Nama Barang\n2.Keluar\n>>> "))
        if data_admin == 1:
            Dftrbrg = {"barang":{0:"laptop ASUS ROG GX800VH",1:"laptop MSI GT83VR 6RF TITAN",2:"laptop ASUS ROG Zephyrus Duo 15",}}
            print("Menambahkan data barang")

            angka =3
            barang_masuk = input("Tambah barang : ")
            Dftrbrg["barang"][angka] = barang_masuk
            angka +=1
            print(Dftrbrg)
            Fungsi_admin()
        

        elif data_admin == 2:
            quit()
            Fungsi_menu()

    elif data_admin == 3:
        Fungsi_menu()

def Fungsi_login():
    print("\nHAI, SILAHKAN LOGIN\n")
    
    login_username = input("usernamemu >>> ")
    for i in range(0,len(Menu_Akun["username"])):
        if login_username == Menu_Akun["username"][i]:
            break
        elif i >= len(Menu_Akun["username"]):
    
            print("Maaf Akun anda belum terdaftar :(")
            quit()
    login_password = int(input("passwordmu >>> "))
    if login_password == Menu_Akun["password"][i]:
        Fungsi_pembelian(i)
    else:

        print("Maaf Akun anda belum terdaftar :(")
        quit()


def Fungsi_buat():
    print("\nINI MENU BUAT AKUN\n")
    Buat_username = input("Masukan username >>> ")
    Menu_Akun["username"][len(Menu_Akun["username"])] = Buat_username

    Buat_password = int(input("Masukan password >>> "))
    Menu_Akun["password"][len(Menu_Akun["password"])] = Buat_password

    buat_uang = int(input("Masukan Jumlah Topup Anda >>> "))
    Menu_Akun["uang"][len(Menu_Akun["uang"])] = buat_uang

    Menu_Akun["voucher"][len(Menu_Akun["voucher"])] = 0
    kepunyaan[len(kepunyaan)] = {0}
    print("SELAMAT AKUN ANDA BERHASIL DIBUAT")
    Fungsi_login()

def Fungsi_menu():
    pilihan = int(input("Sudah punya akun belum? kalau belum silahkan buat akun dulu ya!\n1.Buat Akun\nkalau sudah, silahkan login\n2.Login\n3.Opsi Admin\n4.Keluar\n\n>>> "))
    if pilihan == 1:
        Fungsi_buat()
    elif pilihan == 2:
        Fungsi_login()
    elif pilihan == 3:
        ulang = "ya"
        while ulang== "ya":
            username = "kelompok4"
            password = "kelompok4"
            username = input ("Masukan Username Anda : ")
            password = input ("Masukan Password Anda : ")
            print("\n")
            if username == "kelompok4" and password == "kelompok4":
                print ("SELAMAT DATANG ADMIN")
                print("\n")
                break
            elif print ("Maaf Anda Gagal Login, Mohon Periksa Username dan Password Anda"): 
                ulang = input ("Apakah anda ingin mengulang ya/tidak ?: ").lower()
                ulang == "tidak"
        Fungsi_admin()
        quit()

def ini_voucher(i):
    print("Hallo",Menu_Akun["username"][i],"\nuang kamu sekarang Rp.",Menu_Akun["uang"][i],"\nvoucher kamu",Menu_Akun["voucher"][i])
    print("\n\n(Tekan Enter Untuk Lanjut.....)")
    input()
    print("pilih Paket yang mana nih ?\npilih :\n\n1.Paket Max Bronze\n2.Paket MAX Silver\n3.Paket MAX Gold")
    pilih = int(input(">>> "))
    if pilih == 1:

        print("Kamu ada di Paket Max Bronze nih\nsilahkan pilih : \n\n1.Top-Up 1200 voucher\n2.Top-Up 2800 voucher\n3.Top-Up 5000 voucher")
        pilih = int(input(">>> "))
        if pilih == 1:
    
            print("Apakah Kamu yakin akan membeli 1200 voucher\nseharga Rp.2000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 2000:
            
                    Menu_Akun["voucher"][i] += 1200
                    Menu_Akun["uang"][i] -= 200000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        elif pilih == 2:
    
            print("Apakah Kamu yakin akan membeli 2800 voucher\nseharga Rp.4000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 400000:
            
                    Menu_Akun["voucher"][i] += 2800
                    Menu_Akun["uang"][i] -= 400000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i) 

        elif pilih == 3:
    
            print("Apakah Kamu yakin akan membeli 5000 voucher\nseharga Rp.7000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 700000:
            
                    Menu_Akun["voucher"][i] += 5000
                    Menu_Akun["uang"][i] -= 700000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i) 

        else:
    
            print("tidak ada pilihan")
            input()
            Fungsi_pembelian(i)   

    elif pilih == 2:

        print("Kamu ada di Paket MAX Silver nih\nsilahkan pilih : \n\n1.Top-Up 15000 voucher\n2.Top-Up 30000 voucher\n3.Top-Up 40000 voucher")
        pilih = int(input(">>> "))

        if pilih == 1:
    
            print("Apakah Kamu yakin akan membeli 15000 voucher\nseharga Rp.20000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 2000000:
            
                    Menu_Akun["voucher"][i] += 15000
                    Menu_Akun["uang"][i] -= 2000000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)
            
            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        elif pilih == 2:
    
            print("Apakah Kamu yakin akan membeli 30000 voucher\nseharga Rp.40000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 4000000:
            
                    Menu_Akun["voucher"][i] += 300000
                    Menu_Akun["uang"][i] -= 4000000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)
            
            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        elif pilih == 3:
    
            print("Apakah Kamu yakin akan membeli 40000 voucher\nseharga Rp.52000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 5200000:
            
                    Menu_Akun["voucher"][i] += 40000
                    Menu_Akun["uang"][i] -= 5200000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        else:
    
            print("tidak ada pilihan")
            input()
            Fungsi_pembelian(i)   

    elif pilih == 3:

        print("Kamu ada di Paket MAX Gold nih\nsilahkan pilih : \n\n1.Top-Up 80000 voucher\n2.Top-Up 120000 voucher\n3.Top-Up 200000 voucher")
        pilih = int(input(">>> "))

        if pilih == 1:
    
            print("Apakah Kamu yakin akan membeli 80000 voucher\nseharga Rp.100000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 10000000:
            
                    Menu_Akun["voucher"][i] += 80000
                    Menu_Akun["uang"][i] -= 10000000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        elif pilih == 2:
    
            print("Apakah Kamu yakin akan membeli 120000 voucher\nseharga Rp.120000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 12000000:
            
                    Menu_Akun["voucher"][i] += 120000
                    Menu_Akun["uang"][i] -= 12000000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        elif pilih == 3:
    
            print("Apakah Kamu yakin akan membeli 200000000 voucher\nseharga Rp.220000 ? ")
            pilih = int(input("1.ya\n2.tidak\n>>> "))
            if pilih == 1:
                if Menu_Akun["uang"][i] > 2200000:
            
                    Menu_Akun["voucher"][i] += 200000000
                    Menu_Akun["uang"][i] -= 2200000
                    print("Pembelian berhasil...\n\nvoucher kamu saat ini",Menu_Akun["voucher"][i],"\nUang kamu Rp.",Menu_Akun["uang"][i])
                    print("\n\n(Tekan Enter.....)")
                    input()
                    Fungsi_pembelian(i)
            
            elif pilih == 2:
        
                print("pembelian dibatalkan\n\n(Tekan Enter Untuk Kembali.....)")
                input()
                Fungsi_pembelian(i)

            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   

        else:
    
            print("tidak ada pilihan")
            input()
            Fungsi_pembelian(i)   

    else:

        print("tidak ada pilihan")
        input()
        Fungsi_pembelian(i)

def ini_laptop(i):
    print("Selamat Datang Di Menu Pembelian dan Check laptop\nSilahkan masukan pilihanmu",Menu_Akun["username"][i],":\n\n1.Beli laptop\n2.Check laptop\n3.Kembali\n")
    pilih = int(input(">>> "))
    if pilih == 1:

        print("Silahkan Pilih laptop Yang Ingin Kamu Beli\n\n1.", Dftrbrg["barang"][0],",\n2.", Dftrbrg["barang"][1],",\n3.", Dftrbrg["barang"][2],",\n\nPilih:")
        pilih = int(input(">>> "))
        if pilih == 1:
    
            print("Kamu akan membeli", Dftrbrg["barang"][0],",\nseharga", Menu_Akun["harga"][0],",voucher?\n1.ya\n2.tidak")
            pilih = int(input(">>> "))
        
            if pilih == 1:
                if Menu_Akun["voucher"][i] > 560000:   
                    kepunyaan[i][len(kepunyaan[i])] = Dftrbrg["barang"][0]
                    Menu_Akun["voucher"][i] -= 560000
                    print("Sukses Melakukan Pembelian....\n\n(tekan enter)")
                    input()
                    ini_laptop(i)
                else:
            
                    print("voucher anda kurang :)\n\n(tekan enter untuk kembali...)")
                    input()
                    ini_laptop(i)
            
            elif pilih == 2:
        
                print("Pembelian dibatalkan\n\n(tekan enter untuk kembali...)")
                input()
                ini_laptop(i)
            
            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   
        
        elif pilih == 2:
    
            print("Kamu akan membeli", Dftrbrg["barang"][1],",\nseharga", Menu_Akun["harga"][1],",voucher?\n1.ya\n2.tidak")
            pilih = int(input(">>> "))

            if pilih == 1:
                if Menu_Akun["voucher"][i] > 720000:   
                    kepunyaan[i][len(kepunyaan[i])] = Dftrbrg["barang"][1]
                    Menu_Akun["voucher"][i] -= 720000
                    print("Sukses Melakukan Pembelian....\n\n(tekan enter)")
                    input()
                    ini_laptop(i)
                else:
            
                    print("voucher anda kurang :)\n\n(tekan enter untuk kembali...)")
                    input()
                    ini_laptop(i)
            
            elif pilih == 2:
        
                print("Pembelian dibatalkan\n\n(tekan enter untuk kembali...)")
                input()
                ini_laptop(i)           
            
            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   
        
        elif pilih == 3:
           
            print("Kamu akan membeli", Dftrbrg["barang"][2],",\nseharga", Menu_Akun["harga"][2],", voucher?\n1.ya\n2.tidak")
            pilih = int(input(">>> "))

            if pilih == 1:
                if Menu_Akun["voucher"][i] > 680000:   
                    kepunyaan[i][len(kepunyaan[i])] = Dftrbrg["barang"][2]
                    Menu_Akun["voucher"][i] -= 680000
                    print("Sukses Melakukan Pembelian....\n\n(tekan enter)")
                    input()
                    ini_laptop(i)
                else:
            
                    print("voucher anda kurang :)\n\n(tekan enter untuk kembali...)")
                    input()
                    ini_laptop(i)
            
            elif pilih == 2:
        
                print("Pembelian dibatalkan\n\n(tekan enter untuk kembali...)")
                input()
                ini_laptop(i)
            else:
        
                print("tidak ada pilihan")
                input()
                Fungsi_pembelian(i)   
                        
        else:
    
            print("tidak ada pilihan")
            input()
            Fungsi_pembelian(i) 

    elif pilih == 2:

        print("HAI",Menu_Akun["username"][i],"ini list laptop yang kamu punya :\n")
        for j in range(0,len(kepunyaan[i])):
            print(kepunyaan[i][j])

        print("\n(enter untuk kembali...)")
        input()
        Fungsi_pembelian(i)
    
    elif pilih == 3:
        Fungsi_pembelian(i)
    
    else:

        print("tidak ada pilihan")
        input()
        Fungsi_pembelian(i)

def ubah_data(i):
    print("Menu Ubah Data\npilih data yang akan diubah:\n\n1.username\n2.password\n3.Kembali")
    pilih = int(input(">>> "))
    if pilih == 1:

        username_dulu = Menu_Akun["username"][i]
        username_baru = input("masukan username baru >>> ")
        Menu_Akun["username"][i] = username_baru

        print("Berhasil mengganti username.....\n\nusername dulu anda :",username_dulu,"\nusername baru anda :",Menu_Akun["username"][i])
        input()
        Fungsi_menu()

    elif pilih == 2:

        password_dulu = Menu_Akun["password"][i]
        password_baru = int(input("masukan password baru >>> "))
        Menu_Akun["password"][i] = password_baru

        print("Berhasil mengganti password.....\n\npassword dulu anda :",password_dulu,"\npassword baru anda :",Menu_Akun["password"][i])
        input()
        Fungsi_menu()

    elif pilih == 3:
        Fungsi_login()

    else:

        print("tidak ada pilihan")
        input()
        Fungsi_pembelian(i)   

def Fungsi_pembelian(i): 
    print("===\nHai...",Menu_Akun["username"][i],":)\nSelamat Datang Di TOKO KOMPUTER DAN AKSESORIS\nSilahkan Pilih Menu Dibawah ini :\n1.Beli voucher\n2.Beli Dan Check laptop \n3.Ubah Username atau password\n4.Menu Utama\n5.Keluar\n===")
    pilih = int(input("\npilihanmu\n>>> "))
    if pilih == 1:
        ini_voucher(i)
    elif pilih == 2:
        ini_laptop(i)
    elif pilih == 3:
        ubah_data(i)
    elif pilih == 4:
        Fungsi_menu()
    else:

        print("Terimakasih telah menggunakan program kami -^\nbyee......")
        quit()


Fungsi_menu()
