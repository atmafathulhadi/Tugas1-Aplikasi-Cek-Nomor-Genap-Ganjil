
# Aplikasi Cek Nomor Genap/Ganjil

**Tugas Pemrograman GUI**  
Nama: Atma Fathul Hadi  
NPM: 2210010425  

## 1. Deskripsi Program
Aplikasi ini adalah program berbasis GUI menggunakan Java untuk memeriksa apakah suatu angka merupakan bilangan genap atau ganjil. Selain itu, program ini juga memeriksa apakah angka yang dimasukkan adalah bilangan prima. Program menggunakan komponen GUI yang interaktif untuk memungkinkan pengguna memasukkan angka, melihat hasilnya, dan keluar dari aplikasi.

## 2. Komponen GUI
Aplikasi ini menggunakan komponen GUI berikut:

- **JFrame**: Sebagai jendela utama aplikasi.
- **JPanel**: Untuk mengatur layout dan grup komponen.
- **JLabel**: Menampilkan label teks, seperti judul aplikasi dan label input.
- **JTextField**: Tempat untuk memasukkan angka yang ingin dicek.
- **JButton**: Tombol untuk memeriksa apakah angka genap/ganjil dan untuk keluar dari aplikasi.
- **JOptionPane**: Menampilkan pesan pop-up yang menunjukkan hasil pemeriksaan.

## 3. Logika Program
Program bekerja dengan cara menerima input angka dari pengguna, kemudian memeriksa apakah angka tersebut genap atau ganjil. Jika angka juga merupakan bilangan prima, program akan memberi informasi tersebut. Jika input bukan angka, program akan menampilkan pesan error.

### Kode Terkait:
- **Fungsi untuk Memeriksa Genap/Ganjil dan Prima**  
  Kode berikut digunakan untuk memeriksa apakah angka genap/ganjil dan prima, serta menampilkan hasilnya menggunakan `JOptionPane`:
  ```java
  cek.addActionListener(new ActionListener() {
      @Override
      public void actionPerformed(ActionEvent e) {
          try {
              int number = Integer.parseInt(yea.getText());
              String result = (number % 2 == 0) ? "Genap" : "Ganjil";
              if (isPrime(number)) {
                  result += " dan Prima";
              }
              JOptionPane.showMessageDialog(null, "Angka " + number + " adalah " + result);
          } catch (NumberFormatException ex) {
              JOptionPane.showMessageDialog(null, "Input harus berupa angka!", "Error", JOptionPane.ERROR_MESSAGE);
          }
      }
  });
  ```
  Fungsi `isPrime()` digunakan untuk memeriksa apakah angka merupakan bilangan prima.
  
- **Event untuk Tombol Keluar**  
  Tombol keluar akan menutup aplikasi saat diklik:
  ```java
  keluar.addActionListener(e -> System.exit(0));
  ```

- **Pembatasan Input Hanya Angka**  
  Menggunakan `KeyAdapter` untuk memastikan hanya angka yang dapat dimasukkan di `JTextField`.
  ```java
  yea.addKeyListener(new KeyAdapter() {
      @Override
      public void keyTyped(KeyEvent e) {
          char c = e.getKeyChar();
          if (!Character.isDigit(c)) {
              e.consume();
          }
      }
  });
  ```

## 4. Cara Menjalankan Program
1. Buka program di IDE seperti NetBeans atau Eclipse.
2. Jalankan program.
3. Masukkan angka pada kolom "MASUKKAN ANGKA".
4. Klik tombol "CEK" untuk memeriksa apakah angka tersebut genap/ganjil dan prima.
5. Hasil perhitungan akan ditampilkan di kotak dialog pop-up.
6. Klik "KELUAR" untuk menutup aplikasi.

## 5. Struktur Program
- **ACNomor.java**: Berisi kode utama untuk aplikasi, termasuk komponen GUI dan logika pemrosesan angka.

Screenshot Hasil Program:
![S](https://github.com/atmafathulhadi/Tugas1-Aplikasi-Cek-Nomor-Genap-Ganjil/blob/main/S.png)
  
## 6. Indikator Penilaian
| No  | Komponen         |  Persentase  |
| :-: | ---------------- |   :-----:    |
|  1  | Komponen GUI     |    20%       |
|  2  | Logika Program   |    20%       |
|  3  | Events           |    15%       |
|  4  | Kesesuaian UI    |    15%       |
|  5  | Memenuhi Variasi |    30%       |
|     | **TOTAL**        |    100%      |

---

Aplikasi ini memberikan antarmuka sederhana yang memungkinkan pengguna untuk mengetahui apakah suatu angka merupakan bilangan genap/ganjil dan prima, serta memudahkan interaksi pengguna dengan pesan error dan konfirmasi hasil yang jelas.
