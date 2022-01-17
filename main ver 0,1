//#include  <bits/stdc++.h>
#include <deque>
#include <iostream>
#include <stdio.h>
#include <termios.h>
#include <unistd.h>
using namespace std;

pair<int, int> F(pair<int, int> hvost, int p, int sz){
	if(p==119){
		return(make_pair(hvost.first , (hvost.second + sz-1)%sz ));
	}
	
	if(p==115){
 		return(make_pair(hvost.first , (hvost.second + 1)%sz ));
	}
	
	if(p==100){
		return(make_pair((hvost.first + 1)%sz, hvost.second));
	}
	
	if(p==97){
		return(make_pair((hvost.first - 1+sz)%sz , hvost.second ));
	}
};



int main(){
	struct termios oldt, newt;
	int ch;

	const int sz=20;	
	int i,j,px=0,py=0;
	int zmeya[sz][sz]={0};
	
	pair<int,int> head={1,0};
	
	pair<int,int> hvost={0,0};
	pair<int,int> hvosttemp={0,0};
	
	pair<int,int> eat= {2,2};
	
	zmeya[0][0]=100;
	cout<<"w a s d"<<endl;
	while(1){
		tcgetattr( STDIN_FILENO, &oldt );
		newt = oldt;
		newt.c_lflag &= ~( ICANON | ECHO );
		tcsetattr( STDIN_FILENO, TCSANOW, &newt);
		ch = getchar();
		tcsetattr( STDIN_FILENO, TCSANOW, &oldt);
		if(ch==119){//w
			zmeya[px][py]=ch;
			py=(py+sz-1)%sz;
			head = make_pair(px,py);
			if(head!=eat){
				hvosttemp=F(hvost,zmeya[hvost.first][hvost.second],sz);
				zmeya[hvost.first][hvost.second]=0;
				hvost=hvosttemp;				
			}
			else{
				while(zmeya[eat.first][eat.second] != 0 || eat == head){
					eat.first=rand()%sz;
					eat.second=rand()%sz;
				}
 			}
		}
		if(ch==115){//s
			zmeya[px][py]=ch;
			py=(py+1)%sz;
			head = make_pair(px,py);
			if(head!=eat){
				hvosttemp=F(hvost,zmeya[hvost.first][hvost.second],sz);
				zmeya[hvost.first][hvost.second]=0;
				hvost=hvosttemp;				
			}
			else{
				while(zmeya[eat.first][eat.second] != 0 || eat == head){
					eat.first=rand()%sz;
					eat.second=rand()%sz;
				}
 			}
		}
		if(ch==100){//d
			zmeya[px][py]=ch;
			px=(px+1)%sz;
			head = make_pair(px,py);
			if(head!=eat){
				hvosttemp=F(hvost,zmeya[hvost.first][hvost.second],sz);
				zmeya[hvost.first][hvost.second]=0;
				hvost=hvosttemp;				
			}
			else{
				while(zmeya[eat.first][eat.second] != 0 || eat == head){
					eat.first=rand()%sz;
					eat.second=rand()%sz;
				}
 			}
		}
		if(ch==97){//a
			zmeya[px][py]=ch;
			
			px=(px+sz-1)%sz;
			head = make_pair(px,py);
			if(head!=eat){
				hvosttemp=F(hvost,zmeya[hvost.first][hvost.second],sz);
				zmeya[hvost.first][hvost.second]=0;
				hvost=hvosttemp;				
			}
			else{
				while(zmeya[eat.first][eat.second] != 0 || eat == head){
					eat.first=rand()%sz;
					eat.second=rand()%sz;
				}
 			}
		}
		if(zmeya[px][py]!=0){
			cout<<"geme over";
			exit(0);
		}
		
		system("clear");
		for(i=0;i<sz;i++){
			for(j=0;j<sz;j++){
				if(zmeya[j][i]!=0){
					cout<<"#";
				}
				else{
					if(j==px&&i==py){
						cout<<"0";
					}
					else{
						if(i==eat.second&&eat.first==j){
							cout<<"w";
						}
						else{
							cout<<".";	
						}
					}
				}
			}
			cout<<endl;
		}
		//cout<<eat.first<<" "<<eat.second<<endl;
	}
	return(0);
}

/*int main1(){
	struct termios oldt,newt;
	int ch;
	tcgetattr( STDIN_FILENO, &oldt );
	newt = oldt;
	newt.c_lflag &= ~( ICANON | ECHO );
	tcsetattr( STDIN_FILENO, TCSANOW, &newt );
	ch = getchar();
	tcsetattr( STDIN_FILENO, TCSANOW, &oldt );
	cout<<ch;
	return(0);
}
*/
