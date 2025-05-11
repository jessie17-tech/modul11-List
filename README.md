# modul11-List

#soal 1
def tiga_terbaik(list_angka):
    list_terurut = sorted(list_angka, reverse=True)
    return list_terurut[:3]

angka = [5, 12, 3, 8, 19, 1, 7]

#soal_2
# Program menghitung rata-rata bilangan dari input pengguna
bilangan_list = [] 

while True:
    input_user = input("Masukkan bilangan (atau 'done' untuk selesai): ")
    
    if input_user.lower() == 'done':
        break
    
    try:
        bilangan = float(input_user) 
        bilangan_list.append(bilangan) 
    except ValueError:
        print("Input tidak valid. Masukkan bilangan atau 'done'.")

if bilangan_list:
    rata_rata = sum(bilangan_list) / len(bilangan_list)
    print(f"Rata-rata bilangan yang dimasukkan: {rata_rata:.2f}")
else:
    print("Tidak ada bilangan yang dimasukkan.")


#soal 3
artikel = """
Python adalah bahasa pemrograman yang populer. Dan merupakan bahasa pemrograman tingkat tinggi yang dirancang 
dengan sintaksis yang sederhana dan mudah dibaca, sehingga sangat cocok bagi pemula maupun profesional. Bahasa 
ini pertama kali dikembangkan oleh Guido van Rossum dan dirilis pada tahun 1991. Python digunakan untuk berbagai 
keperluan seperti pengembangan web, analisis data, dan kecerdasan buatan. Bahasa Python mudah dipelajari.
"""

def ekstrak_kata_unik(teks):
    tanda_baca = '''!()-[]{};:'"\,<>./?@#$%^&*_~'''
    for char in tanda_baca:
        teks = teks.replace(char, ' ')
    
    kata_kata = teks.split()
    kata_unik = list(set(kata_kata))
    return kata_unik

kata_unik = ekstrak_kata_unik(artikel)
print("Kata-kata unik dalam artikel:")
for i, kata in enumerate(sorted(kata_unik), 1):
    print(f"{i}. {kata}")
