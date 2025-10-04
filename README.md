#include <stdio.h>

int main() {
    char nama[50], gender;
    int umur;
    float tb, bb, kkal, bb_ideal;
    
    printf("===================================================\n");
    printf("<<< Project Hitung Kalori dan Berat Badan Ideal >>>\n");
    printf("===================================================\n");
    
    printf("Masukkan nama lengkap: ");
    fgets(nama, sizeof(nama), stdin);
    
    printf("Masukkan tinggi badan (cm): ");
    scanf("%f", &tb);
    
    printf("Masukkan berat badan (bb): ");
    scanf("%f", &bb);
    
    printf("Masukkan umur (tahun): ");
    scanf("%d", &umur);
    
    printf("Masukkan gender (P = Pria atau W = Wanita): ");
    scanf(" %c", &gender);
    
    if (gender == 'P' || gender == 'p') {
        //hitung kalori pria
        printf("\n==============================");
        printf("\n<<< Menghitung kalori pria >>>\n");
        printf("==============================\n");
        kkal = (10*bb)+(6.25*tb)-(5*umur)+5;
        printf("Hallo %s", nama);
        printf("Kebutuhan kalori perhari anda sekitar: %.2f kkal/hari", kkal);
        //hitung bb ideal pria
        bb_ideal = (tb-100)-(0.10*(tb-100));
    }
    else {
        //hitung kalori wanita 
        printf("\n================================");
        printf("\n<<< Menghitung kalori wanita >>>\n");
        printf("================================\n");
        kkal = (10*bb)+(6.25*tb)-(5*umur)-161;
        printf("Hallo %s", nama);
        printf("Kebutuhan kalori perhari anda sekitar: %.2f kkal/hari", kkal);
        //hitung bb ideal wanita
         bb_ideal = (tb-100)-(0.15*(tb-100));
    }
    
    //tampilkan bb ideal
    printf("\nBerat badan ideal anda: %.2f kg", bb_ideal);
    
    //cek apakah bb ideal atau tidak
    if (bb >= bb_ideal - 2 && bb <= bb_ideal + 2) {
        printf("\nStatus BB anda : ideal\n");
    }
    else {
        printf("\nStatus BB anda : Tidak ideal\n");
    }
    
    return 0;
}
