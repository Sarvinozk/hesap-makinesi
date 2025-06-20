#include <stdio.h>
#include <stdlib.h>
#include <math.h>

// Temel matematiksel işlemler
double toplama(double a, double b) {
    return a + b;
}

double cikarma(double a, double b) {
    return a - b;
}

double carpma(double a, double b) {
    return a * b;
}

double bolme(double a, double b) {
    if (b == 0) {
        printf("Hata: Sıfıra bölme yapılamaz!\n");
        return 0;
    }
    return a / b;
}

// Sınıf ortalaması hesaplama fonksiyonu
void sinif_ortalama_hesapla() {
    printf("\n=== SINIF ORTALAMA HESAPLAYICI ===\n");
    printf("Problem: Sınıfın bir yarısının ortalaması belli,\n");
    printf("diğer yarısının ortalaması da belli ise genel ortalama nedir?\n\n");
    
    double yarim1_ort, yarim2_ort, genel_ort;
    int ogrenci_sayisi;
    
    printf("Toplam öğrenci sayısını girin: ");
    scanf("%d", &ogrenci_sayisi);
    
    printf("Birinci yarının ortalamasını girin: ");
    scanf("%lf", &yarim1_ort);
    
    printf("İkinci yarının ortalamasını girin: ");
    scanf("%lf", &yarim2_ort);
    
    // Genel ortalama hesaplama
    genel_ort = (yarim1_ort + yarim2_ort) / 2.0;
    
    printf("\n--- SONUÇLAR ---\n");
    printf("Toplam öğrenci sayısı: %d\n", ogrenci_sayisi);
    printf("Her yarıda öğrenci sayısı: %d\n", ogrenci_sayisi/2);
    printf("Birinci yarının ortalaması: %.2f\n", yarim1_ort);
    printf("İkinci yarının ortalaması: %.2f\n", yarim2_ort);
    printf("Sınıfın genel ortalaması: %.2f\n", genel_ort);
}

// Özel problem çözücü (sizin verdiğiniz problem)
void ozel_problem_coz() {
    printf("\n=== ÖZEL PROBLEM ÇÖZÜCÜ ===\n");
    printf("Problem: Sınıf ortalaması 50, yarısının ortalaması 30,\n");
    printf("diğer yarısının ortalaması ortalamanın üstünde.\n");
    printf("Diğer yarının ortalaması kaç olmalı?\n\n");
    
    double sinif_ort = 50.0;
    double yarim1_ort = 30.0;
    double yarim2_ort;
    
    // Matematiksel çözüm: (30 + x) / 2 = 50
    // 30 + x = 100
    // x = 70
    yarim2_ort = (2 * sinif_ort) - yarim1_ort;
    
    printf("--- ÇÖZÜM ---\n");
    printf("Sınıf ortalaması: %.2f\n", sinif_ort);
    printf("Birinci yarının ortalaması: %.2f\n", yarim1_ort);
    printf("İkinci yarının ortalaması: %.2f\n", yarim2_ort);
    printf("Fark: %.2f (ortalamanın %.2f puan üstünde)\n", 
           yarim2_ort - sinif_ort, yarim2_ort - sinif_ort);
    
    // Doğrulama
    double kontrol = (yarim1_ort + yarim2_ort) / 2.0;
    printf("Kontrol: (%.2f + %.2f) / 2 = %.2f ✓\n", 
           yarim1_ort, yarim2_ort, kontrol);
}

// Genel ortalama hesaplayıcı
void genel_ortalama_hesapla() {
    printf("\n=== GENEL ORTALAMA HESAPLAYICI ===\n");
    int n;
    printf("Kaç tane sayının ortalamasını hesaplamak istiyorsunuz? ");
    scanf("%d", &n);
    
    if (n <= 0) {
        printf("Geçersiz sayı!\n");
        return;
    }
    
    double toplam = 0.0;
    double sayi;
    
    for (int i = 1; i <= n; i++) {
        printf("%d. sayıyı girin: ", i);
        scanf("%lf", &sayi);
        toplam += sayi;
    }
    
    double ortalama = toplam / n;
    printf("\nToplam: %.2f\n", toplam);
    printf("Sayı adedi: %d\n", n);
    printf("Ortalama: %.2f\n", ortalama);
}

// Ana menü
void menu_goster() {
    printf("\n=== GELİŞMİŞ HESAP MAKİNESİ ===\n");
    printf("1. Toplama (+)\n");
    printf("2. Çıkarma (-)\n");
    printf("3. Çarpma (*)\n");
    printf("4. Bölme (/)\n");
    printf("5. Sınıf Ortalama Hesapla\n");
    printf("6. Özel Problem Çöz (Sınıf Ortalaması)\n");
    printf("7. Genel Ortalama Hesapla\n");
    printf("8. Çıkış\n");
    printf("================================\n");
}

int main() {
    int secim;
    double sayi1, sayi2, sonuc;
    char devam;
    
    printf("*** GELİŞMİŞ C HESAP MAKİNESİ ***\n");
    printf("Matematik işlemleri ve ortalama hesaplamaları\n");
    
    do {
        menu_goster();
        printf("Seçiminizi yapın (1-8): ");
        
        if (scanf("%d", &secim) != 1) {
            printf("Geçersiz giriş! Lütfen bir sayı girin.\n");
            while (getchar() != '\n');
            continue;
        }
        
        switch (secim) {
            case 1: // Toplama
                printf("\nTOPLAMA İŞLEMİ\n");
                printf("Birinci sayıyı girin: ");
                scanf("%lf", &sayi1);
                printf("İkinci sayıyı girin: ");
                scanf("%lf", &sayi2);
                sonuc = toplama(sayi1, sayi2);
                printf("Sonuç: %.2f + %.2f = %.2f\n", sayi1, sayi2, sonuc);
                break;
                
            case 2: // Çıkarma
                printf("\nÇIKARMA İŞLEMİ\n");
                printf("Birinci sayıyı girin: ");
                scanf("%lf", &sayi1);
                printf("İkinci sayıyı girin: ");
                scanf("%lf", &sayi2);
                sonuc = cikarma(sayi1, sayi2);
                printf("Sonuç: %.2f - %.2f = %.2f\n", sayi1, sayi2, sonuc);
                break;
                
            case 3: // Çarpma
                printf("\nÇARPMA İŞLEMİ\n");
                printf("Birinci sayıyı girin: ");
                scanf("%lf", &sayi1);
                printf("İkinci sayıyı girin: ");
                scanf("%lf", &sayi2);
                sonuc = carpma(sayi1, sayi2);
                printf("Sonuç: %.2f * %.2f = %.2f\n", sayi1, sayi2, sonuc);
                break;
                
            case 4: // Bölme
                printf("\nBÖLME İŞLEMİ\n");
                printf("Birinci sayıyı girin: ");
                scanf("%lf", &sayi1);
                printf("İkinci sayıyı girin: ");
                scanf("%lf", &sayi2);
                if (sayi2 != 0) {
                    sonuc = bolme(sayi1, sayi2);
                    printf("Sonuç: %.2f / %.2f = %.2f\n", sayi1, sayi2, sonuc);
                }
                break;
                
            case 5: // Sınıf ortalama hesapla
                sinif_ortalama_hesapla();
                break;
                
            case 6: // Özel problem çöz
                ozel_problem_coz();
                break;
                
            case 7: // Genel ortalama hesapla
                genel_ortalama_hesapla();
                break;
                
            case 8: // Çıkış
                printf("Hesap makinesi kapatılıyor...\n");
                return 0;
                
            default:
                printf("Geçersiz seçim! Lütfen 1-8 arasında bir sayı girin.\n");
                break;
        }
        
        printf("\nBaşka işlem yapmak istiyor musunuz? (e/h): ");
        scanf(" %c", &devam);
        
    } while (devam == 'e' || devam == 'E');
    
    printf("Teşekkürler! Hesap makinesi kapatılıyor...\n");
    return 0;
}
