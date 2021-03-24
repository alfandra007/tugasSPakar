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
