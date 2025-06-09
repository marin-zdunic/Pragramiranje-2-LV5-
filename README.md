# Pragramiranje-2-LV5-

1. Zad
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

2. Zad
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
