package com.company;

import java.util.*;

// Member
class Member {
    String nama;
    String nomorHp;
    String pekerjaan;

    // Constructor
    Member(String nama, String nomorHp, String pekerjaan){
        this.nama = nama;
        this.nomorHp = nomorHp;
        this.pekerjaan = pekerjaan;
    }

    // Method
    void dataMember(){
        System.out.println(" ------ Data Member ------ ");
        System.out.println(" Nama          : " + this.nama);
        System.out.println(" No HP         : " + this.nomorHp);
        System.out.println(" Pekerjaan     : " + this.pekerjaan);
    }
}

// Admin
class Admin {
    String namaAdmin;
    String id;

    // Constructor
    Admin (String namaAdmin, String id) {
        this.namaAdmin = namaAdmin;
        this.id = id;
    }

    // Method
    void dataAdmin(){
        System.out.print("\n");
        System.out.println(" -------- Admin -------- ");
        System.out.println (" Nama Admin    : " + this.namaAdmin);
        System.out.println (" ID            : " + this.id);
    }
}

public class Main {

    public static void main(String[] args) {
        Admin Lisa = new Admin("Lisa", "12345");
        int pilihan, x = 0, y = 0;
        char alternatif;
        String nama, nomorHp, pekerjaan;

        Scanner input = new Scanner(System.in);
        Member[] dataMember = new Member[1024];

        do {
            System.out.print("\n");
            System.out.println(" ---------- WELCOME ---------- ");
            System.out.println(" ----- Perpustakaan Gwensky ----- ");
            System.out.print("\n");
            System.out.println("1. Daftar Member");
            System.out.println("2. Data Member");
            System.out.println("3. Keluar\n ");

            System.out.print(" Masukkan pilihan : ");
            pilihan = input.nextInt();
            if (pilihan == 1) {
                x++;
                do {
                    Lisa.dataAdmin();
                    System.out.print("\n");

                    System.out.println(" ------ Data Member ----- ");
                    System.out.print("Nama          : ");
                    nama = input.next();
                    System.out.print("No HP         : ");
                    nomorHp = input.next();
                    System.out.print("Pekerjaan     : ");
                    pekerjaan = input.next();
                    System.out.print("\n");
                    dataMember[x] = new Member(nama, nomorHp, pekerjaan);


                    System.out.print(" Ingin Membuat Member ? (y/n) ");
                    alternatif = input.next().charAt(0);
                }while (alternatif == 'n' || alternatif == 'N');
                System.out.print("\n");
                System.out.print("- Selamat Anda Sudah Terdaftar -");
                System.out.print("\n");
            } else if (pilihan == 2) {
                if (x < 1) {
                    System.out.print("\n");
                    System.out.println(" Member Masih Kosong !");
                } else {
                    while (y < x) {
                        y++;
                        System.out.print("\n");
                        System.out.println(" - Member Sudah Ada -");
                        System.out.print("\n");
                        dataMember[y].dataMember();
                        Lisa.dataAdmin();
                    }
                }
            } else {
                return;
            }
            System.out.print("\n");
            System.out.print(" Ingin Kembali Ke Menu ? (y/n) ");
            alternatif = input.next().charAt(0);
        } while (alternatif == 'y' || alternatif == 'Y');
        System.out.print("\n");
        System.out.print("~ Terima Kasih Telah Menggunakan Aplikasi Ini ~");
        System.out.print("\n");
    }
}
