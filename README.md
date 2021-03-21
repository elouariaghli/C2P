# C2P
Convert C to Python
#include <stdio.h>
int main(){
	int m, s, d, u;
	float p;
	printf("Entrer le nombre de minutes: ");
	scanf("%d", &m);
	printf("Entrer le nombre de secondes: ");
	scanf("%d", &s);
	
	d = m * 60 + s;  //Conversion de la duree en secondes
	
	//La 1ère minute est indivisible : Nombre d'unites = 3
	if(d <= 60){
		p = 3 * 1.40;
	}
	else if(d <= 180){  //1,40 pour les 3 premières minutes
		u = d / 20;		//u = nombre d'unites
		if(d % 20 != 0)
			u++;
		p = u * 1.40;
	}
	else{
		u = d / 20;		
		if(d % 20 != 0)
			u++;
		p = 9 * 1.40 + (u - 9) * 1.20;  //Les 3 premières minutes = 9 unites
	}
	
	printf("\nLe cout de la communication est %.2f DH", p);
	return 0;
//Source : www.exelib.net
