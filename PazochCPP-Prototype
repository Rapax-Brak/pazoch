#include <iostream>
#include <cstdlib>
#include <sstream>
#include <string>
#include <ctime>
#include <algorithm>
#include <chrono>
#include <thread>
#include <pthread.h>



using namespace std;

void pickCard(int card);
void oTurn();
void stands();
void tutorial();
int getDeck();
int showSideDeck();
void checkCards();
void play();
void store();
void side();
int getCard();
string visualCard(int card);
int pCard1;
int oCard1;
int oCard2;
int oCard3;
int oCard4;
string vCard1;
int pCard2;
string vCard2;
int pCard3;
string vCard3;
int pCard4;
string vCard4;
int tTotal;
int dTotal;
int dCard;
int tCard;
int decis;



int gameTable [16];
string sideDeck[18] = {"+1", "+2", "+3", "+4", "+5", "+6", "-1", "-2", "-3", "-4", "-5", "-6", "~1", "~2", "~3", "~4", "~5", "~6"};
string boughtCards[20];
int credits = 50;

int main(){
  srand(time(0));
  int dec;

  cout << "Would you like to play a tutorial? (1) Yes (2) No\n";
  cin >> dec;
  switch(dec){
    case 1: tutorial();break;
    case 2: break;
    default: break;
  }
  cout << "(1) Play\n(2) Store\n(3) Side Deck\n";
  cin >> dec;
  switch(dec){
    case 1: play();break;
    case 2: store(); break;
    case 3: side();break;
    default: cout << "You did not select an answer.";
  }
}

void tutorial(){
  cout << "PLACEHOLDER";
}

void play(){
  cout << "Please wait while it loads.\n";
  string HoS;
  oCard1 = getDeck();
  vCard1 = visualCard(oCard1);
  oCard2 = getDeck();
  vCard2 = visualCard(oCard2);
  oCard3 = getDeck();
  vCard3 = visualCard(oCard3);
  oCard4 = getDeck();
  vCard4 = visualCard(oCard4);
  checkCards();

  
  bool stand = false;
  
  while(!stand){
    tCard = getCard();
    cout << "You drew " << tCard << endl;
    tTotal = tTotal + tCard;
    cout << "Your total is " << tTotal << endl;
    cout << "Your side deck is ";showSideDeck();
    if (tTotal >= 20){
      cout << "press 1,2,3,4 or 0 to not pick side deck card\n";
      cin >> decis;
      switch (decis){
        case 1: pickCard(pCard1);break;
        case 2: pickCard(pCard2);break;
        case 3: pickCard(pCard3);break;
        case 4: pickCard(pCard4);break;
        default: break;
        }
    }
    if (dTotal >= 20){
      stand = true;
      stands();
    }
      if (!stand){
      cout << "Press 1, 2, 3 or 4 to select a card press ENTER to not.";
      cin >> decis;
      switch (decis){
        case 1: pickCard(pCard1);break;
        case 2: pickCard(pCard2);break;
        case 3: pickCard(pCard3);break;
        case 4: pickCard(pCard4);break;
        default: break;
      }
      if (dTotal >= 20){
      stand = true;
      stands();
    }
    if (!stand){
      cout << "(h)it or (s)tand" << endl;
      cin >> HoS;
      if (HoS == "H" || HoS == "h"){
      
      }else{
        stand = true;
      }
        oTurn();
      }else {
      
    }
    }
  }
  stands();
  
}

void oTurn(){
    dCard = getCard();
    cout << "\nOpponent drew " << dCard << endl;
    dTotal = dTotal + dCard;
    cout << "Opponent's total is " << dTotal << endl;
    cout << "Press 0 to continue\n\n";
    cin.get();
}

void pickCard(int card){
  string HoS;
  if (card == pCard1){
    if (oCard1 >= 7 && oCard1 <= 13){
      tTotal = tTotal - pCard1; 
    }else if (oCard1 < 7){
      tTotal = tTotal + pCard1;
    }else{
      cout << "+ or -";
      cin >> HoS;
      if(HoS == "+"){
        tTotal = tTotal + pCard1;
      }else {
        tTotal = tTotal - pCard1;
      }
    }
  }else if (card == pCard2){
    if (oCard2 >= 7 && oCard2 <= 13){
      tTotal = tTotal - pCard1; 
    }else if (oCard2 < 7){
      tTotal = tTotal + pCard1;
    }else{
      cout << "+ or -";
      cin >> HoS;
      if(HoS == "+"){
        tTotal = tTotal + pCard2;
      }else {
        tTotal = tTotal - pCard2;
      }
    }
  }else if (card == pCard3){
    if (oCard1 >= 7 && oCard1 <= 13){
      tTotal = tTotal - pCard3; 
    }else if (oCard1 < 7){
      tTotal = tTotal + pCard3;
    }else{
      cout << "+ or -";
      cin >> HoS;
      if(HoS == "+"){
        tTotal = tTotal + pCard3;
      }else {
        tTotal = tTotal - pCard3;
      }
    }
  }else if (card == pCard4){
    if (oCard1 >= 7 && oCard1 <= 13){
      tTotal = tTotal - pCard4; 
    }else if (oCard1 < 7){
      tTotal = tTotal + pCard4;
    }else{
      cout << "+ or -";
      cin >> HoS;
      if(HoS == "+"){
        tTotal = tTotal + pCard4;
      }else {
        tTotal = tTotal - pCard4;
      }
    }
  }else{
    cout << "ERROR!";
  }
 cout << "Your total is " << tTotal << endl;
 cout << "press 0 to continue";
 cin >> decis;
}

void stands(){
  while (dTotal < tTotal && dTotal < 17 && tTotal <= 20){
  oTurn();
  }
  if (dTotal < tTotal && tTotal <= 20){
    cout << "You win 1\n";
  }else if (tTotal < dTotal && dTotal <= 20){
    cout << "You lose 1\n";
  }else if (dTotal == tTotal && dTotal <= 20){
    cout << "You tie 1\n";
  }else if (dTotal == tTotal && dTotal == 20){
    cout << "You tie 2\n";
  }else if (dTotal > 20 && tTotal <= 20){
    cout << "You win 2\n";
  }else if (dTotal <= 20 && tTotal > 20){
    cout << "You lose 2\n";
  }else {
    cout << "TIE.";
  }
}

int showSideDeck() {
  cout << vCard1 << pCard1 << " ";
  cout << vCard2 << pCard2 << " ";
  cout << vCard3 << pCard3 << " ";
  cout << vCard4 << pCard4 << endl;
}
int useSideDeck() {
    
}

int getCard(){
  return rand() % 18 + 1;
}
int getDeck() {
   int card = rand() % 18 + 1;
   int loop;
   while (card == pCard1 || card == pCard2 || card == pCard3 || card == pCard4){
     card = rand() % 18 + 1;
   }
   return card;
}

string visualCard(int card){
      if (card >= 7 && card <= 13){
      return "-";
    }else if (card < 7){
      return "+";
    }else {
      return "~";
    }
    return "+";
}

void store(){
  cout << "PLACEHOLDER";
}

void side(){
  
}

void checkCards(){
  pCard1 = pCard1 + oCard1;
  pCard2 = pCard2 + oCard2;
  pCard3 = pCard3 + oCard3;
  pCard4 = pCard4 + oCard4;
  if (pCard1 >= 7 && pCard1 <= 13){
    pCard1 = pCard1 - 6;
  }else if (pCard1 >= 13){
    pCard1 = pCard1 - 11;
  }else {
    
  }
  if (pCard2 >= 7 && pCard2 <= 13){
    pCard2 = pCard2 - 6;
  }else if (pCard2 >= 13){
    pCard2 = pCard2 - 11;
  }else {
    
  }
  if (pCard3 >= 7 && pCard3 <= 13){
    pCard3 = pCard3 - 6;
  }else if (pCard3 >= 13){
    pCard3 = pCard3 - 11;
  }else {
    
  }
  if (pCard4 >= 7 && pCard4 <= 13){
    pCard4 = pCard4 - 6;
  }else if (pCard4 >= 13){
    pCard4 = pCard4 - 11;
  }else {
    
  }
}
