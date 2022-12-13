# SAEROBOT_TD3_GEII

![TeraTerm affichant l'exécution du programme](https://github.com/hugofnmdev/SAEROBOT_TD3_GEII/blob/main/COM.png?raw=true)

Programme en C++ :

```c
#include "mbed.h"

DigitalIn jack(PTE20);
DigitalIn finCourse(PTE21);
AnalogIn mesureBatterie(A0);
AnalogIn captLigneDroite1(A1);
AnalogIn captLigneDroite2(A2);
AnalogIn captLigneGauche1(A3);
AnalogIn captLigneGauche2(A4);


int main() {
    printf("Jack | FinCourse | MesureBatterie | Droite1 | Droite2 | Gauche1 | Gauche2\n");
    while (1) {
        int jackVal = jack.read();
        int fcVal = finCourse.read();
        double mbVal = mesureBatterie.read(); 
        double d1Val = captLigneDroite1.read();
        double d2Val = captLigneDroite2.read();
        double g1Val = captLigneGauche1.read();
        double g2Val = captLigneGauche2.read();
        printf("%4d | %9d | %14.2f | %7.2f | %7.2f | %7.2f | %7.2f\n", 
            jackVal, 
            fcVal, 
            mbVal, 
            d1Val, 
            d2Val,
            g1Val,
            g2Val
        );
        wait(3);
    }
}
```