# digunakan untuk berbagi kode sumber
## sc penjumlahan java


import java.util.Scanner;

class PenjumlahanMatriks{

    public static void main(String[] args) {
        buatMatriks();
    }

    public static void buatMatriks(){
        //set kolom baris
        String alert = "nilai yang dapat di input paling kecil adalah ";
        Scanner input = new Scanner(System.in);
        int kolom, baris, nMatriks;
        
        //set baris
        System.out.print("masukan Jumlah baris matriks : ");
        baris   = input.nextInt();
        while (baris < 1) {
            System.out.println(alert+ " 1!!");
            System.out.print("masukan Jumlah baris matriks : ");
            baris  = input.nextInt();
        }

        //set kolom
        System.out.print("masukan Jumlah kolom matriks : ");
        kolom   = input.nextInt();
        while (kolom < 1) {
            System.out.println(alert+ " 1!!");
            System.out.print("masukan Jumlah kolom matriks : ");
            kolom  = input.nextInt();
        }

        //set jumlah
        System.out.print("masukan Jumlah matriks : ");
        nMatriks   = input.nextInt();
        while (nMatriks < 2) {
            System.out.println(alert+ " 2!!");
            System.out.print("masukan Jumlah matriks : ");
            nMatriks  = input.nextInt();
        }
        
        //buat matriks dari nilai diatas
        int matriks[][][] = new int[nMatriks][baris][kolom];
        for (int i = 0; i < nMatriks; i++) {
            for (int j = 0; j < baris; j++) {
                for (int j2 = 0; j2 < kolom; j2++) {
                    System.out.print("Masukkan nilai matriks " + (i+1) + "[" + (j+1) +"]["+ (j2+1) +"] = ");
                    matriks[i][j][j2] = input.nextInt();
                }
            }
        }

        for (int i = 0; i < nMatriks; i++) {
            System.out.println("matriks " + (i + 1) + " : ");
            for (int j = 0; j < baris; j++) {
                System.out.print("[");
                for (int j2 = 0; j2 < kolom; j2++) {
                    System.out.print(matriks[i][j][j2]);
                    if (j2 + 1 != baris) System.out.print(" ");
                }
                System.out.print("]");
                System.out.println();
            }
        }

        int hasil[][] = new int[baris][kolom];
        for (int i = 0; i < nMatriks; i++) {
            for (int j = 0; j < baris; j++) {
                for (int j2 = 0; j2 < kolom; j2++) {
                    // System.out.print("Masukkan nilai matriks "  + "[" + (j + 1) + "][" + (j2 + 1) + "] = ");
                    hasil[j][j2] += matriks[i][j][j2];
                }
            }
        }
        
        System.out.println();
        System.out.println("hasil Penjumlahan Matriks : ");
        for (int j = 0; j < baris; j++) {
            System.out.print("[");
            for (int j2 = 0; j2 < kolom; j2++) {
                System.out.print(hasil[j][j2]);
                if (j2 + 1 != baris)
                    System.out.print(" ");
            }
            System.out.print("]");
            System.out.println();
        }

}

}
