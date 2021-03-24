# tugasSPakar
tugas kuliah sistempakar
Dicky Alfandra 1184019

# Analisis BFS
Penerapan ini menggunakan Python dictionary sebagai list/daftar kedekatan dengan struktur data kamus yang mana node memiliki list simpanan dari node yang berdekatan.

       peta1 =  {'A':set(['B']),
                'B':set(['C','E','A']),
                'C':set(['D','F','E']),
                'D':set(['C']),
                'E':set(['C','G','B']),
                'F':set(['C','H','K']),
                'G':set(['E','H']),
                'H':set(['F','I']),
                'I':set(['H','J']),
                'J':set(['I']),
                'K':set(['F'])}
 
         

       def bfs(graf, mulai, tujuan):
           queue = [[mulai]]
           visited = set()
ini merupakan  definisi dari pembentukan bfs, visited merupakan daftar yang digunakan untuk melacak node

       while queue:     
        jalur = queue.pop(0)
        print("\n --------------------- \n")
        print("jalur = ", jalur)
        print("queue = ", queue)  
merupakan kondisi queue yang akan dilakukan dalam kodingan sebelumnya

      state = jalur[-1]
        print("state = ", state)
menyimpan node yang dipilih ke variabel state, misal jalur = C,B maka simpan B ke variabel state

       if state == tujuan:
            return jalur
untuk mengecek state apakah sama dengan tujuan jika ya maka return jalur
jika tidak sama maka akan dilakukan sebagai berikut

       elif state not in visited:
            # jika state tidak ada di visited maka cek cabang
            for cabang in graf.get(state, []): #cek semua cabang dari state
                if cabang not in visited:
                    jalur_baru = list(jalur) #masukkan isi dari variabel jalur ke variabel jalur_baru
                    jalur_baru.append(cabang) #update/tambah isi jalur_baru dengan cabang
                    queue.append(jalur_baru) #update/tambah queue dengan jalur_baru
                    
untuk menandai state yang sudah dikunjungi akan dilakukan 

            print("queue = ", queue)
            visited.add(state)
            print("visited = ", visited)
untuk mengecek isi antrian maka akan dilakukan 

       isi = len(queue)
        print("isi = ",isi)
        if isi == 0:
         print("Tidak ditemukan")
         
hasil yang akan dilakukan ditampilkan dengan kodingan

       print("HASIL = ",bfs(peta1,'C','J'))
       print("\n peta = ",peta1)
