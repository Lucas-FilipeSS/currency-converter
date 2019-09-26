# Tutorial 2 APAP
## Pertanyaan
1. Cobalah untuk menambahkan sebuah store dengan mengakses link berikut:
http://localhost:8080/store/add?idStore=1&nama=shapipi&keterangan=Toko%20Elekt
ronik&followers=100
Apa yang terjadi? Jelaskan mengapa hal tersebut dapat terjadi.

Answer: Yang terjadi ialah Whitelabel Error, hal ini bisa terjadi dikarenakan pada 
	saat saya mengerjakan itu saya belum membuat viewnya. View tersebut berupa
	file html yang terdapat di folder template.

2. Cobalah untuk menambahkan sebuah store dengan mengakses link berikut:
http://localhost:8080/store/add?idStore=3&nama=shapipi&keterangan=Toko%20Elekt
ronik
Apa yang terjadi? Jelaskan mengapa hal tersebut dapat terjadi.

Answer: Yang terjadi ialah Whitelabel Error, hal ini terjadi dikarenakan pada link
	tersebut tidak terdapat isi untuk parameter followers. Dengan begitu isi
	dari followers ialah null dan karenanya terjadi whitelabel error.

3.Jika Papa APAP ingin melihat store shapee, link apa yang harus diakses?

Answer: jika Papa APAP ingin melihat semua store yang sudah terdaftar, maka Papa APAP
	dapat mengakses link http://localhost:8080/store/view-all . Dan jika Papa
	ingin melihat atau mengecek apakah salah store yang Papa APAP inginkan sudah
	masuk atau belum bisa menggunakan link 
	http://localhost:8080/store/view?idStore={nomor}
	dengan mencari tahu nomor dari store yang ingin dicek oleh Papa APAP dan
	memasukkannya ke {nomor}.

4. Tambahkan 1 contoh store lainnya sesukamu. Lalu cobalah untuk mengakses
   http://localhost:8080/store/view-all , apa yang akan ditampilkan? Sertakan juga
   bukti screenshotmu.

Answer: tampilannya ialah semua store yang sudah didaftarkan. Saya coba mencontohkan
		dengan link localhost:8080/store/add?idStore=2&nama=shapopo&keterangan=Toko Sepatu&followers=99
		![image](https://user-images.githubusercontent.com/34976128/65139861-8fac4900-da37-11e9-9fd1-b399b70a6733.png)
	

# Tutorial 3 APAP
## Pertanyaan
1. Pada class ProductDb, terdapat method findByStoreModelId, apakah kegunaan dari
   method tersebut?

Answer: Kegunaan dari method findByStoreModelId ialah method tersebut akan melakukan
	pencarian product yang terdapat pada objek StoreModel. Method ini akan
	mereturn list yang berisi product yang ditemukan.

2. Pada class StoreController, jelaskan perbedaan method addStoreFormPage dan
   addStoreSubmit?

Answer: Dapat dilihat pada method addStoreFormPage menggunakan method GET. Hal ini
	berarti pada method addStoreFormPage akan mengambil form yang telah ada.
	Form ini bertujuan untuk menambahkan store. Sedangkan untuk method
	addStoreSubmit, method yang dilakukan ialah POST. Yang berarti pada method
	ini ketika dijalankan akan memposting data yang sudah diisi pada form
	ke database untuk disimpan

3. Jelaskan kegunaan dari JPA Repository

Answer: JPA Repository memudahkan untuk melakukan CRUD (CREATE, READ, UPDATE, serta
	DELETE) pada database.

4. Sebutkan dan jelaskan di bagian kode mana sebuah relasi antara StoreModel dan
   ProductModel dibuat?

Answer: Pada ProductModel terdapat pada gambar dibawah ini
	![gambar](https://user-images.githubusercontent.com/34976128/65691733-8f492900-e09b-11e9-97a2-6bb2667f9195.png)

	Untuk StoreModel terdapat pada gambar dibawah ini
	![gambar](https://user-images.githubusercontent.com/34976128/65691851-c4557b80-e09b-11e9-8073-dc75714fc5a5.png)
	
	Dapat dilihat di gambar, terhubungnya relasi tersebut disebabkan pada 
	ProductModel memiliki atribut dengan tipe relasi ManyToOne kepada StoreModel.
	Dan StoreModel memliki atribut dengan tipe relasai OneToMany dan dipetakkan
	ke ProductModel. Selain itu juga, pada ProductModel terdapat JoinColumn
	dengan StoreModel berdasarkan storeid.

5. Jelaskan kegunaan FetchType.LAZY, CascadeType.ALL, dan FetchType.EAGER

Answer: FetchType.LAZY berfungsi untuk membuat sebuah object dipanggi sesuai kebutuhan.
	Pada contoh tutorial ini ialah listProduct pada StoreModel menggunakan
	FetchType.LAZY. Jadi ketika StoreModel diload, listProduct tidak ikut 
	terload kecuali kita memanggil atau mengakses listProduct tersebut dengan 
	getter.

	Untuk FetchType.EAGER kebalikan dari LAZY. Jadi sebuah object akan langsung
	terpanggil atau terload ketika kita mengakses object yang berelasi dengannya.
	Sebagai contoh pada tutorial 3, storeModel yang menggunakan EAGER. Jadi
	ketika ProductModel diakses, storeModel akan diload juga.

	Untuk CascadeType.ALL, object yang diberikan CascadeType.ALL memiliki
	semua tipe Cascade yaitu PERSIST, REMOVE, REFRESH, MERGE, dan DETACH. Object
	tersebut juga memiliki semua tipe Hibernate yaitu REPLICATE, SAVE_UPDATE, 
	dan LOCK. Dengan menggunakan CascadeType.ALL memudahkan untuk melakukan
	CRUD (CREATE, READ, UPDATE, dan DELETE) pada suatu data.

## What I did not understand
Cara kerja JPA Repository, lalu penggunakan Serializable.