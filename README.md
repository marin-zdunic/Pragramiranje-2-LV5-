# Pragramiranje-2-LV5-

a)
1. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int broj;
    do{
        printf("Unesi troznamenkasti broj: ");
        scanf("%d", &broj);
    }while(broj < 100 || broj > 999);

    int sto = broj/100;
    int des = (broj/10)%10;
    int jed = broj%10;

    int max = sto;
    if(des > max) max = des;
    if(jed > max) max = jed;

    int umnozak = 0;
    if(max == sto) umnozak = des*jed;
    if(max == des) umnozak = sto*jed;
    if(max == jed) umnozak = sto*des;

    printf("Najveca znamenka: %d ", max);
    printf("\nUmnozak preostale dvije: %d ", umnozak);
   return 0;
   }
   
2. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n, broj, brojac = 0;

    do{
        printf("Unesi broj: ");
        scanf("%d", &n);
    }while(n < 5 || n > 19);

    for(int i = 1; i < n+1; i++){
        printf("Unesi %d. broj: ", i);
        scanf("%d", &broj);
        if(broj % 7 == 0 && broj > 15){
            brojac++;
        }
    }

    printf("\nUkupno brojeva djeljivih sa 7 i vecih od 15: %d", brojac);
   return 0;
   }
   
3. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      char a, b;

    printf("Unesi prvi znak: ");
    scanf(" %c", &a);
    printf("Unesi drugi znak: ");
    scanf(" %c", &b);

    if(a < b){
        for(int i = a+1; i < b; i++){
            printf("%c ", i);
        }
    }else if(a > b){
        for(int i = a-1; i > b; i--){
            printf("%c ", i);
        }
    }else{
        printf("Ista slova!");
    }
   return 0;
   }

b)
1. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n, sum = 0;
    int niz[20];
    float sr_vr;

    do {
        printf("Unesi broj elemenata (izmedu 2 i 20): ");
        scanf("%d", &n);
    } while (n <= 1 || n > 20);

    for(int i = 0; i < n; i++){
        printf("Unesi %d. element: ", i+1);
        scanf("%d", &niz[i]);
        sum += niz[i];
    }

    sr_vr = (float)sum/n;

    printf("Brojevi veci od srednje vrijednosti:\n ");
    for(int i = 0; i < n; i++){
        if(niz[i] > sr_vr && niz[i] % 2 == 0){
            printf("%d ", niz[i]);
        }
    }
    int nep_veci = 0, nep_manji = 0;
    for(int i = 0; i < n; i++){
        if(niz[i] % 2 != 0){
            if(niz[i] < sr_vr) nep_manji++;
            if(niz[i] > sr_vr) nep_veci++;
        }
    }
    printf("\nBroj neparnih, a manjih od srednje vrijednosti: %d ", nep_manji);
    printf("\nBroj neparnih, a vecih od srednje vrijednosti %d ", nep_veci);

    return 0;
   
   }

2. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n;
    float niz[20];
    float sr_vr;

    do {
        printf("Unesi broj elemenata (izmedu 5 i 50): ");
        scanf("%d", &n);
    } while (n < 5 || n > 49);

    for(int i = 0; i < n; i++){
        printf("Unesi %d. element: ", i+1);
        scanf("%f", &niz[i]);
    }

    printf("\nElementi u obrnutom redoslijedu:\n");
    for (int i = n - 1; i >= 0; i--) {
        if (fmod(niz[i], 1.0) == 0 && (int)niz[i] % 2 == 0) {
            printf("%.2f ", niz[i] * 2);
        } else {
            printf("%.2f ", niz[i]);
        }
    }

    return 0;
   }

3. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n;
    float niz[77];

    do {
        printf("Unesi broj elemenata (izmedu 8 i 77): ");
        scanf("%d", &n);
    } while (n <= 7 || n >= 77);

    for(int i = 0; i < n; i++){
        printf("Unesi %d. element: ", i+1);
        scanf("%f", &niz[i]);
    }

    float zb_int1 = 0, zb_int2 = 0;
    int brojac = 0;

    for(int i = 0; i < n; i++){
        if(niz[i] >= -10 && niz[i] <= 10){
            zb_int1 += niz[i];
        }
        if(niz[i] >= 30 && niz[i] <= 40){
            zb_int2 += niz[i];
            brojac++;
        }
    }

    if(brojac != 0){
        printf("\nZbroj elemenata unutar intervala [-10, 10] je: %.2f\n", zb_int1);
    }else{
        printf("\nNema elemenata unutar intervala [-10, 10].\n");
    }

    if(brojac > 0){
        float sr_vr = zb_int2 / brojac;
        printf("Srednja vrijednost elemenata unutar intervala [30, 40] je: %.2f\n", sr_vr);
    }else{
        printf("Nema elemenata unutar intervala [30, 40].\n");
    }
    return 0;
   }

c) 
1. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n;
    int m[3][3];
    int sum = 0;

    do {
        printf("Unesi broj n (n < 4): ");
        scanf("%d", &n);
    } while (n >= 4 || n < 1);

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            printf("Unesi element [%d][%d]: ", i, j);
            scanf("%d", &m[i][j]);
        }
    }

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            int broj = m[i][j];
            if (abs(broj) >= 10 && abs(broj) <= 99) {
                sum += broj;
            }
        }
    }

    printf("\nZbroj svih dvoznamenkastih brojeva: %d\n", sum);

    return 0;
   }

2. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n;
    float m[4][4];
    float min, max;

    do {
        printf("Unesi broj n (n < 5): ");
        scanf("%d", &n);
    } while (n >= 5 || n < 1);

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            printf("Unesi element [%d][%d]: ", i, j);
            scanf("%f", &m[i][j]);
        }
    }

    min = max = m[0][0];

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (m[i][j] < min)
                min = m[i][j];
            if (m[i][j] > max)
                max = m[i][j];
        }
    }

    float raz = max - min;
    printf("\nRazlika najveceg i najmanjeg elementa: %.2f\n", raz);

    return 0;
   }

3. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      int n, poz_flag = 0;
    float m[4][4];
    float min, max;
    float umnozak = 1;

    do {
        printf("Unesi broj n (2 < n < 5): ");
        scanf("%d", &n);
    } while (n <= 2 || n >= 5);

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            printf("Unesi element [%d][%d]: ", i, j);
            scanf("%f", &m[i][j]);
        }
    }

    for (int i = 0; i < n; i++) {
        if (m[i][i] > 0) {
            umnozak *= m[i][i];
            poz_flag = 1;
        }
    }

    if (poz_flag) {
        printf("\nUmnozak pozitivnih brojeva na glavnoj dijagonali je: %.2f\n", umnozak);
    } else {
        printf("\nNa glavnoj dijagonali nema pozitivnih brojeva.\n");
    }
    return 0;
   }

d)
1. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      char tekst[101];
    int brojac = 0;
    int duzina = 0;

    printf("Unesi string (maks. 100 znakova): ");
    fgets(tekst, sizeof(tekst), stdin);

    tekst[strcspn(tekst, "\n")] = '\0';

    duzina = strlen(tekst);

    for (int i = 0; i < duzina; i++) {
        if (tekst[i] == 'a' || tekst[i] == 'A') {
            brojac++;
        }
    }

    if (duzina > 0) {
        float postotak = ((float)brojac / duzina) * 100;
        printf("Slovo 'a' pojavljuje se %d puta (%.2f%% od ukupnog broja znakova).\n", brojac, postotak);
    } else {
        printf("String je prazan.\n");
    }

    return 0;
   }

2. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      char tekst[101];
    int malo_a = 0, veliko_a = 0;

    printf("Unesite string (maks 100 znakova): ");
    fgets(tekst, sizeof(tekst), stdin);

    tekst[strcspn(tekst, "\n")] = '\0';

    for (int i = 0; tekst[i] != '\0'; i++) {
        if (tekst[i] == 'a') {
            malo_a++;
        } else if (tekst[i] == 'A') {
            veliko_a++;
        }
    }

    if (malo_a > veliko_a) {
        printf("Slovo 'a' se pojavilo vise puta (%d puta).\n", malo_a);
    } else if (veliko_a > malo_a) {
        printf("Slovo 'A' se pojavilo vise puta (%d puta).\n", veliko_a);
    } else if (malo_a == 0 && veliko_a == 0) {
        printf("Slovo 'a' ni 'A' se ne pojavljuju u stringu.\n");
    } else {
        printf("Slovo 'a' i 'A' se pojavljuju jednak broj puta (%d puta).\n", malo_a);
    }
    return 0;
   }
   
3. Zad
   #include <stdio.h>
   #include <stdlib.h>
   
   int main(){
      char tekst[51];
    int brojac = 0;

    printf("Unesi string (maks.50 znakova): ");
    fgets(tekst, sizeof(tekst), stdin);

    tekst[strcspn(tekst, "\n")] = '\0';

    for (int i = 0; tekst[i] != '\0'; i++) {
        char c = tolower(tekst[i]);
        if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
            brojac++;
        }
    }

    printf("Ukupan broj samoglasnika: %d\n", brojac);

    return 0;
   }

e)
1. Zad
   #include <stdio.h>
   #include <stdlib.h>
   #include <math.h>

   float Stozac(float r, float h){
     float volumen = 1.0/3.0*pow(r,2)*M_PI*h;
     return volumen;
   }
   
   int main(){
      float r = 4;
    float h = 2;
    float vol = Stozac(r,h);

    printf("Volumen: %.2f", vol);

   return 0;
   }

2. Zad
   #include <stdio.h>
   #include <stdlib.h>
   #include <math.h>

   int Znamenke(int n){
    if (n < 10)
        return 1;
    else if (n < 100)
        return 2;
    else
        return 3;
   }

   int main(){
      int n = 25;
    int rez = Znamenke(n);
    printf("Broj %d ima oznaku: %d\n", n, rez);

   return 0;
   }

3. Zad
   #include <stdio.h>
   #include <stdlib.h>
   #include <math.h>

   float Srednja(int x, int y){
    int sum = 0;
    int brParni = 0;

    if (x > y) {
        int temp = x;
        x = y;
        y = temp;
    }

    for (int i = x + 1; i < y; i++) {
        if (i % 2 == 0) {
            sum += i;
            brParni++;
        }
    }

    if (brParni == 0)
        return 0;
    else
        return (float)sum / brParni;
   }

   int main(){
      int x = 2;
    int y = 10;

    float rez = Srednja(x, y);

    if (rez == 0)
        printf("Nema parnih brojeva između %d i %d.\n", x, y);
    else
        printf("Srednja vrijednost parnih brojeva izmedu %d i %d: %.2f\n", x, y, rez);
   
   return 0;
   
   }
   
   
   
   
