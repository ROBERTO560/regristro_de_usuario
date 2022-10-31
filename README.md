# regristro_de_usuario
codigo para regristro y muestra de divisas y inversiones
#include <iostream>
#include <cstdlib>
#include <string>
#include <conio.h>

#define USER "roberto"
#define PASS "sopa"

using namespace std;

int main() {
	
	string usuario, password, u;
	
	int opc;
	int opc1;
	int inver1, rinver1;
	int inver2, rinver2;
	int inver3, rinver3;
	float can_usa, can_peso, can_eur, resultado, resultado1, resultado2;
	bool ingresa = false;
	int contador = 0;
	
	cout <<"\t\t\tBIENVENIDO POR FAVOR DIGITE LA OPCION QUE DESEA" << endl;
	cout <<"\n\n\t1.CONVERTIR DE USA A COP" << endl;
	cout <<"\t2.CONVERTIR DE COP A USA" << endl;
	cout <<"\t3.CONVERTIR DE EUR A COP" << endl;
	cout <<"\t4.HACER UN INVERSION" << endl;
	cout <<"\t5.SALIR" << endl;
	cin >> opc;
	system("cls");
	
if(opc>0 && opc<6){
	switch(opc){
		case 1:
			cout <<"\n\tdigite la cantidad de dolares: " << endl;
			cin >> can_usa;
			resultado = can_usa*4.918;
			system("cls");
			cout <<"\n\tEN PESOS COLOMBIANOS TIENE UN VALOR DE: " << resultado <<"\tMIL PESOS"  << endl;
			break;
		case 2:
			cout <<"\n\tDIGITE LA CANTIDAD DE PESOS: " <<endl;
			cin >>can_peso;
			resultado1 = can_peso/4.918;
			system("cls");
			cout <<"\n\tEN DOLARES AMERICANOS TIENE UN VALOR DE : " << resultado1 <<"\tdolares" << endl;
			break;
		case 3: 
	    	cout <<"\n\tDIGITE LA CANTIDAD EN EUROS: " <<endl;
	    	cin >>can_eur;
	    	resultado2 = can_eur*4.843;
	    	system("cls");
	    	cout << "\n\tEN PESOS COLOMBIANOS TIENE UN VALOR DE: " << resultado2 <<"\tMIL PESOS" << endl;
		    break;
		case 4:
			do{
				system("cls");
			    cout <<"\t\t\tINTRUDISCA SU USUARIO" << endl;
			    cout <<"\t\t\t---------------------" << endl;
			    cout <<"\n\t*";
			    getline(cin,u);
			    cout <<"\n\tUsuario: ";
			    getline(cin,usuario);
		    	cout <<"\n\tPassword: ";
			    //getline(cin, password);
			    char caracter;
			    caracter = getch();
			    password = "";
			    while(caracter != 13){
			    	password.push_back(caracter);
			    	cout << "*";
			    	caracter = getch();
				}
		    	
		    	if(usuario == USER && password == PASS ){
				ingresa = true;  
		    	} else {
				cout <<"\n\tEL USUARIO INVALIDO" << endl;
				cin.get();
				contador ++;
		  	}
            } while(ingresa == false && contador < 3);
            
            if(ingresa == false){
            	cout << "\n\t\los sentimos pero usted no puede entrar" << endl;	
			} else {
				system("cls");
				cout <<"\n\t\tSELECCIONE LA OPCIONES DE INVERSION: " << endl;
				cout <<"\n\t1.INVERSION MENOR A 100 USD" << endl;
				cout <<"\n\t2.INVERSION DE 100 USD A 500 USD" << endl;
				cout <<"\n\t3.INVERSION DE 500 USD A 1000 USD" << endl;
				cin >> opc1;
				if (opc1 > 0 && opc1 < 4){
					system("cls");
					switch(opc1){ 
						case 1:
							cout <<"\n\n\tPORFAVOR INTRODUSCA LA CANTIDAD QUE DESEA INVERTIR:" << endl;
							    cin >> inver1;
							if(inver1 > 0 && inver1 < 100){
								system("cls");
							    rinver1 = inver1*0.03;
							    cout <<"\n\n\tEL USUARIO:" << USER << endl;
							    cout <<"\n\n\tCON NUMERO DE CEDULA: 0218U81282"  << endl;
							    cout << "\n\n\tPLAZO: 6 MESES" << endl;
							    cout <<"\n\n\tSU GANANCIA ES DE: " << rinver1+inver1 <<"\tDOLARES" <<endl;
							} else{
								cout << "\n\n\tOPCION INVALIDA" << endl;
							}
							break;
						case 2:
							cout <<"\n\n\tPORFAVOR INTRODUSCA LA CANTIDAD QUE DESEA INVERTIR:" << endl;
							    cin >> inver2;
							if(inver2 > 100 && inver2 < 500){
								system("cls");
							    rinver2 = inver2*0.05;
							    cout <<"\n\n\tEL USUARIO:" << USER << endl;
							    cout <<"\n\n\tCON NUMERO DE CEDULA: 0218U81282"  << endl;
							    cout << "\n\n\tPLAZO: 6 MESES" << endl;
							    cout <<"\n\n\tSU GANANCIA ES DE: " << rinver2+inver2 <<"\tDOLARES" <<endl;
							} else{
								cout << "\n\n\tOPCION INVALIDA" << endl;
							}
							break;
						case 3:
							cout <<"\n\n\tPORFAVOR INTRODUSCA LA CANTIDAD QUE DESEA INVERTIR:" << endl;
							    cin >> inver3;
							if(inver3 > 500 && inver3 < 1000){
								system("cls");
							    rinver3 = inver3*0.07;
							    cout <<"\n\n\tEL USUARIO:" << USER << endl;
							    cout <<"\n\n\tCON NUMERO DE CEDULA: 0218U81282"  << endl;
							    cout << "\n\n\tPLAZO: 6 MESES" << endl;
							    cout <<"\n\n\tSU GANANCIA ES DE: " << rinver3+inver3 <<"\tDOLARES" <<endl;
							} else{
								cout << "\n\n\tOPCION INVALIDA" << endl;
							}
							break;
					}
					
				}
			}
	    case 5:
	    	return 0;
}
}else{
	cout << "opcion invalida";
}
    cin.get();
    cin.get();
	return 0;
}
