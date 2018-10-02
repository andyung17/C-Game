# C++-Game
/********************************************************************************************************
//Name:Andy Ung	& Brayden Mills																			*	
//Date: June 15 2018																					*
//Purpose:Game pack with 5 games																		*	
//Data Dictionary:																						*
//					words... string of words (holds 12 words)											* 	
//					answer...Holds the answer from the user (string)									*
//					leng...Length of the answer (int)													*
//					answer2...Holds the answer from the user (string)									*
//																										*
//			Andy:Documented and coded main menu,hangman,tictactoe,guessinggame							*
//			Brayden:Documented and coded maze game and the interaction with the main menu				*
//																										*	
//																										*		
********************************************************************************************************/

//Bringing in libaries 
#include <iostream>
#include <string>
#include <ctype.h>
#include <cstdlib>
#include <time.h>
#include <windows.h>
using namespace std;

//Declaring functions/Games
void hangman(string words[12]);
void tictactoe();
void guessinggame();
void Mazegame();

//Starting program
main()
{
	//Declaring variables
	string words[12]={"extravagant","bewildered","conscience","trampoline","hippopotamus","commensurate",
	"remuneration","flabbergasted","accommodate","pronunciation","authoritarian","advantageous"};
	string answer;
 	int leng,answer2;
	
	//Outputting intro screen
	cout<<endl<<" .----------------.  .----------------.  .----------------.  .----------------.    ";
	cout<<endl<<"| .--------------. || .--------------. || .--------------. || .--------------. |  ";
	cout<<endl<<"| |    ______    | || |      __      | || | ____    ____ | || |  _________   | |  ";
	cout<<endl<<"| |  .' ___  |   | || |     /  \\     | || ||_   \\  /   _|| || | |_   ___  |  | | ";
	cout<<endl<<"| | / .'   \\_|   | || |    / /\\ \\    | || |  |   \\/   |  | || |   | |_  \\_|  | |";
	cout<<endl<<"| | | |    ____  | || |   / ____ \\   | || |  | |\\  /| |  | || |   |  _|  _   | |";
	cout<<endl<<"| | \\ `.___]  _| | || | _/ /    \\ \\_ | || | _| |_\\/_| |_ | || |  _| |___/ |  | |";
	cout<<endl<<"| |  `._____.'   | || ||____|  |____|| || ||_____||_____|| || | |_________|  | | "; 
	cout<<endl<<"| |              | || |              | || |              | || |              | |";  
	cout<<endl<<"| '--------------' || '--------------' || '--------------' || '--------------' |";  
	cout<<endl<<" '----------------'  '----------------'  '----------------'  '----------------' ";                                                                                 
    cout<<endl<<".----------------.  .----------------.  .----------------.  .----------------. ";
	cout<<endl<<"| .--------------.|| .--------------. || .--------------. || .--------------. |";
	cout<<endl<<"| |   ______     ||| |      __      | || |     ______   | || |  ___  ____   | |";
	cout<<endl<<"| |  |_   __ \\   ||| |     /  \\     | || |   .' ___  |  | || | |_  ||_  _|  | |";
	cout<<endl<<"| |    | |__) |  ||| |    / /\\ \\    | || |  / .'   \\_|  | || |   | |_/ /    | |";
	cout<<endl<<"| |    |  ___/   ||| |   / ____ \\   | || |  | |         | || |   |  __'.    | |";
	cout<<endl<<"| |   _| |_      ||| | _/ /    \\ \\_ | || |  \\ `.___.'\\  | || |  _| |  \\ \\_  | |";
	cout<<endl<<"| |  |_____|     ||| ||____|  |____|| || |   `._____.'  | || | |____||____| | |";
	cout<<endl<<"| |              ||| |              | || |              | || |              | |";       
	cout<<endl<<"| '--------------'|| '--------------' || '--------------' || '--------------' |";
	cout<<endl<<"'----------------'  '----------------'  '----------------'  '----------------' "; 
	//Changing colour
	system ("color  0A");
	
    cout<<endl<<"By: Andy Ung & Brayden Mills";
	
	//Asking user if they would like to play  
    cout<<"\n\nWould you Like to Play our Game Pack? ";
    cin>>answer;
	
	//Getting length of the answer      
    leng=answer.length();

	//Upper casing all the letters
	for (int i=0;i<leng;i++)
	{
		//Uppercasing each letter
		answer[i]=toupper(answer[i]);
	}
	//Loops until answer doesnt equal yes   
    while ((answer=="YES") || (answer=="YEAH") || (answer=="SURE"))
    {
    	//Change the backround and text colour
		system ("color  0F");
		//System clear screen
    	system("cls");
    	
    	//Outputting options and asking what they would like to play
    	cout<<"Hangman (1)\nTicTacToe (2)\nMaze Game (3)\nGuessing Game (4)\nExit (5)"<<endl<<"Enter the Number Corresponding for What you Would You Like To Play (#)? ";
    	cin>>answer2;
    	
    	//If theyre answer2 is 1
    	if (answer2==1)
    	{
    		//Calls to the hangman function (game)
    		hangman(words);
    		//Clear screen
	    	system ("cls");
	    	//Asking the user if they would like to play a new game
	    	cout<<"Would you like to play a new game? ";
	    	cin>>answer;
	    	//Getting the length of the answer
	    	leng=answer.length();
	    	//Looping the amount of times as the length
	    	for (int i=0;i<leng;i++)
			{
				//Uppercasing each letter
				answer[i]=toupper(answer[i]);
			}
		}
		//If answer2 equals 2
		else if (answer2==2)
    	{
    		//calls to the tictactoe function
    		tictactoe();
    		//Clear screen
	    	system ("cls");
	    	//Asking the user if they would like to play a new game
	    	cout<<"Would you like to play a new game? ";
	    	cin>>answer;
	    	//Getting the length of the answer
	    	leng=answer.length();
	    	//Looping the amount of times as the length
	    	for (int i=0;i<leng;i++)
			{
				//Uppercasing each letter
				answer[i]=toupper(answer[i]);
			}
		}
		//if answer 2 equals 4
		else if (answer2==3)
    	{
    		//calls maze game
    		Mazegame();
			//Asking the user if they would like to play a new game
	    	cout<<"Would you like to play a new game? ";
	    	cin>>answer;
	    	//Getting the length of the answer
	    	leng=answer.length();
	    	//Looping the amount of times as the length
	    	for (int i=0;i<leng;i++)
			{
				//Uppercasing each letter
				answer[i]=toupper(answer[i]);
			}	
		}
		//If answer 2 equals 5 
		else if (answer2==4)
    	{
    		//Calls to the guessing game
    		guessinggame();
    		//Clear screen
	    	system ("cls");
	    	//Asking the user if they would like to play a new game
	    	cout<<"Would you like to play a new game? ";
	    	cin>>answer;
	    	//Getting the length of the answer
	    	leng=answer.length();
	    	//Looping the amount of times as the length
	    	for (int i=0;i<leng;i++)
			{
				//Uppercasing each letter
				answer[i]=toupper(answer[i]);
			}
		}
		//If answer2 equals 6
		else if (answer2==5)
		{
			//Sets answer to NO
			answer="NO";
		}
		//All other options are not entered
		else
		{
			//Outputs invalid option
			cout<<"Invalid option";
			//Pauses screen
			system("pause");
			//Clear screen
	    	system ("cls");
	    	//Asking the user if they would like to play a new game
	    	cout<<"Would you like to play a game? ";
	    	cin>>answer;
	    	//Getting the length of the answer
	    	leng=answer.length();
	    	//Looping the amount of times as the length
	    	for (int i=0;i<leng;i++)
			{
				//Uppercasing each letter
				answer[i]=toupper(answer[i]);
			}
		}
	}
	//Outputing thanks for playing in ascii art
	cout<<endl<<" _____  _              _           ___    _____  _            _";
	cout<<endl<<"|_   _|| |_  ___  ___ | |_  ___   | | |  |  _  || | ___  _ _ |_| ___  ___";
	cout<<endl<<"  | |  |   || .'||   || '_||_ -|  |_  |  |   __|| || .'|| | || ||   || . |";
	cout<<endl<<"  |_|  |_|_||__,||_|_||_,_||___|    |_|  |__|   |_||__,||_  ||_||_|_||_  |";
	cout<<endl<<"                                                        |___|        |___|";
	cout<<endl<<"      _.-'''''-._";
	cout<<endl<<"    .' _     _   '."; 
	cout<<endl<<"   /   (o)   (o)   \\";  
	cout<<endl<<"  |                 |";  
	cout<<endl<<"  |  \\           /  |";   
	cout<<endl<<"   \\  '.       .'  /";
	cout<<endl<<"    '.  `'---'`  .'";
	cout<<endl<<"BYE   '-._____.-'";
}
//Declaring function
void hangman(string words[12])
{
	/********************************************************************************************************
	//Name:Andy Ung																							*	
	//Date: June 15 2018																					*
	//Purpose:Hangman game																					*	
	//Data Dictionary:																						*
	//					response...The answer the user enters to enter or exit hangman game (string) 		* 	
	//					displayword...The word the user has to get written in * (string)					*
	//					word...The word the user has to guess												*
	//					letterguess...array that holds the letter the users guesses							*
	//					stringGen...Variable to hold a value from 1-10	(int)								*
	//					wordlength...Length of the word	(int)												*
	//					wrong...How many times the user can get a wrong guess (int)							*
	//					pos...Position 	(int)																*		
	//					correctletter...How many correct letters are in the word (int)						*							
	//					win...Win counter (int)																*	
	//					lose...Lose counter (int)															*
	//					lettercount...counting how many letters the user has inputted (int)					*
	//																										*		
	********************************************************************************************************/
	//Declaring functions
	string wordDec(int stringGen,string word,string words[]);
	void lives (int wrong,int lettercount,char letterguess[],string displayword);
	void endscreen(string displayword,string word,string &response,string letter,char letterguess[],int &win,int &lose,int wrong,int lettercount,int correctletter);
	int duplicate=0;
	
	//Random number each time
	srand(time(NULL));
	//Declaring variables
	string response,letter,displayword,word;
	char letterguess[26];
	int stringGen,wordlength,wrong=9,pos,correctletter=0,win=0,lose=0,lettercount;
	
	//Outputing the intro of hangman
	system ("color  F0");
	system ("cls");
	cout<<endl<<" __  __     ______     __   __     ______     __    __     ______     __   __    ";
	cout<<endl<<"/\\ \\_\\ \\   /\\  __ \\   /\\ \"-.\\ \\   /\\  ___\\   /\\ \"-./  \\   /\\  __ \\   /\\ \"-.\\ \\   ";
	cout<<endl<<"\\ \\  __ \\  \\ \\  __ \\  \\ \\ \\-.  \\  \\ \\ \\__ \\  \\ \\ \\-./\\ \\  \\ \\  __ \\  \\ \\ \\-.  \\  ";
	cout<<endl<<" \\ \\_\\ \\_\\  \\ \\_\\ \\_\\  \\ \\_\\\\\"\\_\\  \\ \\_____\\  \\ \\_\\ \\ \\_\\  \\ \\_\\ \\_\\  \\ \\_\\\\\"\\_\\ ";
	cout<<endl<<"  \\/_/\\/_/   \\/_/\\/_/   \\/_/ \\/_/   \\/_____/   \\/_/  \\/_/   \\/_/\\/_/   \\/_/ \\/_/ ";
	//New line 
	cout<<endl;   
	cout<<endl<<"\t-------------";
    cout<<endl<<"\t|           |";
    cout<<endl<<"\t|           O";
    cout<<endl<<"\t|          O O";
    cout<<endl<<"\t|           O";
    cout<<endl<<"\t|          /|\\";
    cout<<endl<<"\t|         / | \\";
    cout<<endl<<"\t|        /  |  \\";
    cout<<endl<<"\t|          / \\";
    cout<<endl<<"\t|         /   \\";
    cout<<endl<<"\t|        /     \\";
    cout<<endl<<"\t|       /       \\";
    cout<<endl<<"\t|";
    cout<<endl<<"\t|";
    cout<<endl<<"\t|";
    cout<<endl<<"-------------------------------";
    //Asking if the user wants to play
    cout<<endl<<"\tWould you like to play? ";
	cin>>response;
	//Upper casing all the characters of their answer
	for (int i=0;i<response.length();i++)
	{
		//Uppercasing letter
		response[i]=toupper(response[i]);
	}
	//Clear screen
	system("cls");
	//Enter the program if they say yes
	while ((response!="NO") || (response=="YES") || (response=="YEAH") || (response=="SURE"))
	{
		system ("color  F0");
		//Clear screen
		system("cls");
		//Setting the lives 
		wrong=9;
		//Setting the letter count to 0
		lettercount=0;
		//Generating a random number
		stringGen=(rand() % 12);
		//Calling to function to set the word for the user
		word=wordDec(stringGen,word,words);
		//Word length
		wordlength=word.length();
		//Count of the amount of letters in the word
		correctletter=wordlength;
		//Assign the output word to stars
		displayword.assign(wordlength,'*');
		//Displays the word and the actual word
		lives (wrong,lettercount,letterguess,displayword);
		//Asking the user for a letter
		cout<<endl<<"Enter a letter-->";
		cin>>letter;
		//Entering the letter into the array
		letterguess[0]=letter[0];
		//Loop to lowercase the letter
		for (int i=0;i<letter.length();i++)
		{
			//lowering the letter
			letter[i]=tolower(letter[i]);
		}
		//Loop until the user has no lives or they're no more letters to guess
		while ((wrong>0) && (correctletter!=0))
		{
			//Finding the position of the letter they entered
			pos=word.find(letter[0]);
			//Calls to the decloration of word function
			wordDec(stringGen,word,words);
			//If the position is higher than the wordlength or is lower than 0
			if ((pos<0) || (pos>wordlength)) 
			{
				//Wrong subtract 1
				wrong--;
				//Calling to the lives function
				lives (wrong,lettercount,letterguess,displayword);
				//Calls to the decloration of word function
				wordDec(stringGen,word,words);
			}
			//if the position is equal to or bigger than 0 and less than or equal to wordlength
			else if ((pos>=0) && (pos<=wordlength))
			{	
				//Subtractsing one from correctletter
				correctletter--;
				//Calls to the decloration of word function
				wordDec(stringGen,word,words);
				//Replacing the symbols with the correct letter guessed
				displayword.replace(pos,1,letter);
				//Replacing the original word letter (correct) with symbols
				word.replace(pos,1,"*");
				//Finding position of the letter
				pos=word.find(letter[0]);
				//Loop to change the correct letter entered until there is no more in the word
				while ((pos>=0) && (pos<=wordlength))
				{
					//Calls to the decloration of word function
					wordDec(stringGen,word,words);
					//Changes the display word by the correct letter entered
					displayword.replace(pos,1,letter);
					//Changes the actual word with a star (correct letter)
					word=word.replace(pos,1,"*");
					//Finds the position of the letter
					pos=word.find(letter[0]);
					//Correctletter subtract one
					correctletter--;
				}
			}
			//Add one to letter count
			lettercount++;
			//Calling to the decloration of the word
			wordDec(stringGen,word,words);
			//If the correctletter cannot equal 0 and wrong cannot equal 0
			if ((correctletter!=0) && (wrong!=0))
			{
				//Setting duplicate to 1
				duplicate=1;
				//Loops when duplicate is bigger than 0
				while (duplicate>0)
				{
					//Sets duplicate to 0
					duplicate=0;
					//Clear screen
					system("cls");
					//Calls to the lives function
					lives (wrong,lettercount,letterguess,displayword);
					//Asking user for a letter
					cout<<endl<<"Enter another letter-->";
					cin>>letter;
					//Lowercasing the letter
					for (int i=0;i<letter.length();i++)
					{
						//Lowers letter
						letter[i]=tolower(letter[i]);
					}
					//loops for how many characters of letters are in the array
					for (int i=0;i<lettercount;i++)
					{
						//sets myletter to the first letter 
						char myletter = letter[0];
						//Sets guesses to letterguesses position of i
						char guesses = letterguess[i];
						//if guesses is equal to letter
						if (guesses==myletter)
						{
							//add one to duplicate
							duplicate++;
						}	
					}
				}
			}
			//Fill the letterguess with the letter	
			letterguess[lettercount]=letter[0];			
		}
		//System clear screen
		system ("cls");
		//Redeclaring word
		word=wordDec(stringGen,word,words);
		//Checking if any exit conditions exit
		if (wrong==0)
		{
			//Calls to the end screen function
			endscreen(displayword,word,response,letter,letterguess,win,lose,wrong,lettercount,correctletter);
		} 
		//Checking if any exit conditions exit
		else if ((correctletter==0) && (wrong>0))
		{
			//Calls to the end screen function
			endscreen(displayword,word,response,letter,letterguess,win,lose,wrong,lettercount,correctletter);
		}
	}
	//Setting the backround and text colour
	system ("color  00");
}
//Declaring functions
string wordDec(int stringGen,string word,string words[])
{
	//if stringgen is equal to 0
	if (stringGen==0)
		{
			//Setting the word to the first word of the array
			word=words[0];
		}
		//if stringgen is equal to 1
		else if (stringGen==1)
		{
			//Setting the word to the second word of the array
			word=words[1];
		}
		//if stringgen is equal to 2
		else if (stringGen==2)
		{
			//Setting the word to the third word of the array
			word=words[2];
		}
		//if stringgen is equal to 3
		else if (stringGen==3)
		{
			//Setting the word to the fourth word of the array
			word=words[3];
		}
		//if stringgen is equal to 4
		else if (stringGen==4)
		{
			//Setting the word to the fifth word of the array
			word=words[4];
		}
		//if stringgen is equal to 5
		else if (stringGen==5)
		{
			//Setting the word to the six word of the array
			word=words[5];
		}
		//if stringgen is equal to 6
		else if (stringGen==6)
		{
			//Setting the word to the seventh word of the array
			word=words[6];
		}
		//if stringgen is equal to 7
		else if (stringGen==7)
		{
			//Setting the word to the eighth word of the array
			word=words[7];
		}
		//if stringgen is equal to 8
		else if (stringGen==8)
		{
			//Setting the word to the nineth word of the array
			word=words[8];
		}
		//if stringgen is equal to 9
		else if (stringGen==9)
		{
			//Setting the word to the tenth word of the array
			word=words[9];
		}
		//if stringgen is equal to 10
		else if (stringGen==10)
		{
			//Setting the word to the eleventh word of the array
			word=words[10];
		}
		//if stringgen is equal to 11
		else if (stringGen==11)
		{
			//Setting the word to the twelfth word of the array
			word=words[11];
		}
		//Returning word
		return(word);
}
//Stages of hangman
void lives (int wrong,int lettercount,char letterguess[],string displayword)
{
	//when wrong is equal to 9
	if (wrong==9)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman  
			cout<<endl<<"\t-------------";
			cout<<endl<<"\t|           |";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"\t|";
			cout<<endl<<"-------------------------------";
			//outputting the display word
			cout<<endl<<"The word is "<<displayword;
	}
	//When wrong equals 8
	else if (wrong==8)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman   
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
		//Outputting display word	
	    cout<<endl<<"The word is "<<displayword;
	}
	//When wrong equals 7
	else if (wrong==7)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman   
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|	   O O";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";	
	    cout<<endl<<"The word is "<<displayword;
	}//When wrong equals 6
	else if (wrong==6)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman  
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          O O";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
		//Outputting display word	
	    cout<<endl<<"The word is "<<displayword;
	}
	//When wrong equals 5
	else if (wrong==5)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman 
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          O O";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
		//Outputting display word	
	    cout<<endl<<"The word is "<<displayword;
	}
	//When wrong equals 4	
	else if (wrong==4)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman  		
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          O O";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          /|";
	    cout<<endl<<"\t|         / |";
	    cout<<endl<<"\t|        /  |";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
		//Outputting display word	
	    cout<<endl<<"The word is "<<displayword;
	}
	//When wrong equals 3
	else if (wrong==3)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          O O";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          /|\\";
	    cout<<endl<<"\t|         / | \\";
	    cout<<endl<<"\t|        /  |  \\";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";	
	    //Outputting display word
	    cout<<endl<<"The word is "<<displayword;
	}
	//When wrong equals 2
	else if (wrong==2)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman 
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          O O";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          /|\\";
	    cout<<endl<<"\t|         / | \\";
	    cout<<endl<<"\t|        /  |  \\";
	    cout<<endl<<"\t|          /";
	    cout<<endl<<"\t|         /";
	    cout<<endl<<"\t|        /";
	    cout<<endl<<"\t|       /";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
		//Outputting display word	
	    cout<<endl<<"The word is "<<displayword;	
	}
	//When wrong equals 1
	else if (wrong==1)
	{
		//Clear screen
		system ("cls");
		//Outtputing lives to user
		cout<<"\tLIVES LEFT: "<<wrong;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loops to output all the letters used
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the stage of hangman 
		cout<<endl<<"\t-------------";
		cout<<endl<<"\t|           |";
		cout<<endl<<"\t|           O";
		cout<<endl<<"\t|          O O";
		cout<<endl<<"\t|           O";
		cout<<endl<<"\t|          /|\\";
		cout<<endl<<"\t|         / | \\";
	    cout<<endl<<"\t|        /  |  \\";
	    cout<<endl<<"\t|          / \\";
	    cout<<endl<<"\t|         /   \\";
	    cout<<endl<<"\t|        /";
	    cout<<endl<<"\t|       / ";
		cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
	    //Outputting display word
	    cout<<endl<<"The word is "<<displayword;
	}
}
//End screen
void endscreen(string displayword,string word,string &response,string letter,char letterguess[],int &win,int &lose,int wrong,int lettercount,int correctletter)
{
	//If wrong is equal to 0
	if (wrong==0)
	{
		//Lose plus one
		lose++;
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Looping the amount of letters in the array
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count subtract 1
			if (i==lettercount-1)
			{
				//Only outputs letter
				cout<<letterguess[i];
			}
			//When i doesnt equal to lettercount minus 1
			else
			{
				//Output letter with a comma
				cout<<letterguess[i]<<",";
			}	
		} 
		//Outputting the user lost the game followed by the correct word  
		cout<<endl<<"\n\tYou lost the game. The word was "<<word;
		//Outputting the win and lose counters
		cout<<endl<<"\t------------------------------";
		cout<<endl<<"\t|             |              |";
		cout<<endl<<"\t|   Wins:"<<win<<"    |    Lose:"<<lose<<"    |"; 
		cout<<endl<<"\t|             |              |";
		cout<<endl<<"\t------------------------------"<<endl;
		//Ouputting the hangman
		cout<<endl<<"\t-------------";
	    cout<<endl<<"\t|           |";
	    cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          O O";
		cout<<endl<<"\t|           O";
	    cout<<endl<<"\t|          /|\\";
	    cout<<endl<<"\t|         / | \\";
	    cout<<endl<<"\t|        /  |  \\";
		cout<<endl<<"\t|          / \\";
	    cout<<endl<<"\t|         /   \\";
	    cout<<endl<<"\t|        /     \\";
	    cout<<endl<<"\t|       /       \\";
		cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"\t|";
	    cout<<endl<<"-------------------------------";
	    //Asking if the user wants to play again
	    cout<<endl<<"\n\n\tWould you like to play again? ";
		cin>>response;
		//Looping for response length	
		for (int i=0;i<response.length();i++)
		{
			//Uppercasing all letters
			response[i]=toupper(response[i]);
		}
	}
	//Outputting when correctletter is 0 and wrong is bigger than 0
	else if ((correctletter==0) && (wrong>0))
	{
		//Adding one to win
		win++;
		//Ouputting letter used
		cout<<endl<<"\t---------------------------";
		cout<<endl<<"\t|       Letters used      |";
		cout<<endl<<"\t|-------------------------|";
		cout<<endl<<"\t";
		//Loop for how many letters are in the array
		for (int i=0;i<lettercount;i++)
		{
			//if i is equal to letter count minus 1
			if (i==lettercount-1)
			{
				//Ouputs the letter in the array
				cout<<letterguess[i];
			}
			//When i is not equal to letter count minus 1
			else
			{
				//Ouputs letter and comma
				cout<<letterguess[i]<<",";
			}	
		}   
		//Changing backround and text colours	
		system ("color  0E");
		//Outputting they won and the word
		cout<<endl<<"\n\tYou got the word;"<<displayword<<".You win!";
		cout<<endl<<"\t------------------------------";
		cout<<endl<<"\t|             |              |";
		//Outputting the wins and loses
		cout<<endl<<"\t|   Wins:"<<win<<"    |    Lose:"<<lose<<"    |"; 
		cout<<endl<<"\t|             |              |";
		cout<<endl<<"\t------------------------------"<<endl;
		cout<<endl<<"\t\t      OOOOOOOOOOO";	         
		cout<<endl<<"\t         OOOOOOOOOOOOOOOOOOO";
		cout<<endl<<"\t     OOOOOO  OOOOOOOOO  OOOOOO"; 
		cout<<endl<<"\t   OOOOOO      OOOOO      OOOOOO";
		cout<<endl<<"\t OOOOOOOO  #   OOOOO  #   OOOOOOOO";
		cout<<endl<<"\t OOOOOOOOOO    OOOOOOO    OOOOOOOOOO";
		cout<<endl<<"\tOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOO";
		cout<<endl<<"\tOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOO";
		cout<<endl<<"\tOOOO  OOOOOOOOOOOOOOOOOOOOOOOOO  OOOO";
		cout<<endl<<"\t OOOO  OOOOOOOOOOOOOOOOOOOOOOO  OOOO";
		cout<<endl<<"\t  OOOO   OOOOOOOOOOOOOOOOOOOO  OOOO";
		cout<<endl<<"\t    OOOOO   OOOOOOOOOOOOOOO   OOOO";
		cout<<endl<<"\t      OOOOOO   OOOOOOOOO   OOOOOO";
		cout<<endl<<"\t         OOOOOO         OOOOOO";
		cout<<endl<<"\t             OOOOOOOOOOOO";
		//Asking if they want to play again
		cout<<endl<<"\n\n\tWould you like to play again? ";
		cin>>response;	
		//Loop for the length of the response
		for (int i=0;i<response.length();i++)
		{
			//Uppercasing all the letters
			response[i]=toupper(response[i]);
		}
	}
	//Changing backround and text colours
	system ("color  0F");
}
//Tictactoe game
void tictactoe ()
{
	/********************************************************************************************************
	//Name:Andy Ung																							*	
	//Date: June 15 2018																					*
	//Purpose:TicTacToe	game																				*	
	//Data Dictionary:																						*
	//					tictactoe...The board of the game (holds char)										*
	//					vert...Vertical portion for the board (int)											*		
	//					horz...Horizontal portion for the board (int)										*
	//					length...Length of the response (int)												*	
	//					length2...Length of response2 (int)													*
	//					win...Player 1 is the winner (int)													*
	//					win2...Player 2 or computer is the winner (int)										*
	//					namecounter...Counter in which it ask for the names of the user (int)				*
	//					reccuring...counter for replaying games does not preform excessive task (int)		*
	//					wincounter...Win counter for player 1 (int)						   					*
	//					winwounter2...win counter for player 2 or computer (int)							*
	//					randnum...Random number (int)														*
	//					compexit...Computer exiting after preforming a move (int)							*
	//					tie...When both players tie (int)													*
	//					response...Answer if the user wants to play the game (sting)						*
	//					reponse2...Users response if they want to replay the game (sting)					*
	//					player1...The name of the player 1 (sting)											*
	//					player2...The name of player 2 (sting)												*
	//																										*		
	********************************************************************************************************/
	
	//Clear screen
	system ("cls");
	//Declaring functions
	void board(char tictactoe[][3]);
	void wincondition(char tictactoe[][3],int &win,int &win2);
	int computerpos(int randnum,char tictactoe[][3],int compexit);

	//Brings in random numbers
	srand(time(NULL));
	
	//Declaring variables
	char tictactoe[3][3];
	int vert,horz,length,length2,win=0,win2=0,namecounter=0,reccuring=0,wincounter=0,wincounter2=0,randnum,compexit=0,tie=0;
	string response,response2="YES",player1,player2;
		
	//Filling in each spot in the array with a space
	for (int j=0;j<3;j++)
	{
		//Filling in the rows
		for (int i=0;i<3;i++)
		{
			//Filling the spot with a space
			tictactoe[j][i]=' ';
		}
	}
	
	//Outputting tictactoe in ascii art
	cout<<endl<<"_________  ________  ______  _________  ________   ______  _________  ______   ______";       
	cout<<endl<<"/________/\\/_______/\\/_____/\\/________/\\/_______/\\ /_____/\\/________/\\/_____/\\ /_____/\\";      
	cout<<endl<<"\\__.::.__\\/\\__.::._\\/\\:::__\\/\\__.::.__\\/\\::: _  \\ \\\\:::__\\/\\__.::.__\\/\\:::_ \\ \\\\::::_\\/_";     
	cout<<endl<<"   \\::\\ \\     \\::\\ \\  \\:\\ \\  __ \\::\\ \\   \\::(_)  \\ \\\\:\\ \\  __ \\::\\ \\   \\:\\ \\ \\ \\\\:\\/___/\\   ";
	cout<<endl<<"    \\::\\ \\    _\\::\\ \\__\\:\\ \\/_/\\ \\::\\ \\   \\:: __  \\ \\\\:\\ \\/_/\\ \\::\\ \\   \\:\\ \\ \\ \\\\::___\\/_  ";
	cout<<endl<<"     \\::\\ \\  /__\\::\\__/\\\\:\\_\\ \\ \\ \\::\\ \\   \\:.\\ \\  \\ \\\\:\\_\\ \\ \\ \\::\\ \\   \\:\\_\\ \\ \\\\:\\____/\\ ";
	cout<<endl<<"      \\__\\/  \\________\\/ \\_____\\/  \\__\\/    \\__\\/\\__\\/ \\_____\\/  \\__\\/    \\_____\\/ \\_____\\/ ";

	//Asking which function to pull up
	cout<<"\n\n\tWould You Like to Play Against the Computer,Player or Quit? ";
	cin>>response;
	
	//Getting the length of the word
	length=response.length();

	//Upper casing all the letters
	for (int i=0;i<length;i++)
	{
		//Uppercasing each letter
		response[i]=toupper(response[i]);
	}
	
	//Loop to run the tictactoe against computer
	while ((response=="COMPUTER") && (response2=="YES") || (response2=="SURE") || (response2=="YEAH"))
	{
		//Clearing screen
		system ("cls");
		if (reccuring==1)
		{
			for (int j=0;j<3;j++)
			{
				for (int i=0;i<3;i++)
				{
					//Sets position to a space
					tictactoe[j][i]=' ';
					//Setting tie to 0
					tie=0;
				}
			}
		}
		
		//Checks if namecounter is 0
		if (namecounter==0)
		{
			//Asking for the names of the players
			cout<<"Enter your name Player 1-> ";
			cin>>player1;
			//System clear screen			
			system ("cls");
			//Add one to namecounter
			namecounter++;
		}
		
		//Redeclaring variables
		reccuring=0;
		win=0;
		win2=0;
	
		//Calling to the board of tictactoe
		board(tictactoe);
		
		//Checking if the game is over, if not ask the player for the positon 
		if ((win==0) && (win2==0))
		{
			//Ask the player for the position
			do{	
			cout<<endl<<player1<<" what position (A#) (B#)--> ";
			cin>>vert>>horz;
			}
			//Keeps asking the user if the spot is filled with something else than a space
			while (tictactoe[vert][horz]!=' ');
			
			//fills the position with an O
			tictactoe[vert][horz]='O';
			
			//Calls to the board function
			board(tictactoe);
			
			//Checks to see if any player wins
			wincondition(tictactoe,win,win2);
			
			//Adding one to tie
			tie++;
		}
		
		//Checks if any players won 
		if ((win==0) && (win2==0)&&(tie <9))
		{
			//Loop until the computer inserted an x
			while (compexit!=1)
			{
				//Calling to the computer picking function
				compexit=computerpos(randnum,tictactoe,compexit);
			}
			//Reseting the exit for computer
			compexit=0;
			
			//Calling to the board function
			board(tictactoe);
			
			//Checking if any players won
			wincondition(tictactoe,win,win2);
			
			//Adding one to tie
			tie++;
		}
		
		//If the player wins (three in a row)
		if (win==1) 
		{
			//Add one to the win counter
			wincounter++;
			
			//Outputting the winner
			cout<<endl<<player1<<" is the Winner!";
			
			//Can work on the computer score
			cout<<endl<<"Score\n"<<player1<<" wins:"<<wincounter<<endl<<"Computer wins:"<<wincounter2;
			
			//Asking user if they would like to play again
			cout<<endl<<"Would you like to play again?";
			cin>>response2;
			
			//Adding one to reccuring
			reccuring++;
			
			//Getting length of the word
			length=response2.length();
			
			//Uppercasing all the letters
			for (int i=0;i<length;i++)
			{
				//Uppercasing letter
				response2[i]=toupper(response2[i]);
			}
		}
		//If the computer won
		else if  (win2==1)
		{
			//Add one to the wincounter2
			wincounter2++;
			
			//Outputting the computer won
			cout<<endl<<"The Computer is the Winner!";
			//Can work on the computer score
			cout<<endl<<"Score\n"<<player1<<" wins:"<<wincounter<<endl<<"Computer wins:"<<wincounter2;
			//Asking if they want to play again
			cout<<endl<<"Would you like to play again?";
			cin>>response2;
			//Add one to reccuring
			reccuring++;
			//Getting the length of response2
			length=response2.length();
			
			//Looping when i is less than length
			for (int i=0;i<length;i++)
			{
				//Uppercasing all the letters
				response2[i]=toupper(response2[i]);
			}
		}
		//When both the user and computer tie
		else if (tie==9)
		{
			//Outputting tie game
			cout<<"\nTie Game";
			//Outputting scores
			cout<<endl<<"Score\n"<<player1<<" wins:"<<wincounter<<endl<<"Computer wins:"<<wincounter2;
			//Asking if they want to play again
			cout<<endl<<"Would you like to play again?";
			cin>>response2;
			//Add one to reccuring
			reccuring++;
			//Getting the length of response2
			length=response2.length();
			//Looping when i is less than length
			for (int i=0;i<length;i++)
			{
				//Uppercasing all the letters
				response2[i]=toupper(response2[i]);
			}
		} 
	}
	//Launching the player program	
	while ((response=="PLAYER") && (response2=="YES"))  
	{
		if (reccuring==1)
		{
			for (int j=0;j<3;j++)
			{
				for (int i=0;i<3;i++)
				{
					//Setting current position of the array to a blank space
					tictactoe[j][i]=' ';
					//Setting tie to 0
					tie=0;
				}
			}
		}
		
		//System clear screen
		system("cls");
		
		//Redeclaring variables
		win=0; 
		win2=0;
		reccuring=0;
		
		//Only asking users on the first loop
		if (namecounter==0)
		{
			//Asking for the names of the players
			cout<<"Enter your name Player 1-> ";
			cin>>player1;
			//System clear screen			
			system ("cls");
			cout<<"Enter your name Player 2-> ";
			cin>>player2;
			//Clearscreen
			system ("cls");
			//Add on to name counter
			namecounter++;
		}
		
		//call function to bring the board up
		board(tictactoe);
		
		//Asking user where they want to place it if they havent won
		if ((win==0) && (win2==0))
		{
			//Ask the user for the position they would like
			do{
			cout<<endl<<player1<<" what position (A#) (B#)--> ";
			cin>>vert>>horz;
			}while (tictactoe[vert][horz]!=' ');
			
			//Fills the spot with an O		
			tictactoe[vert][horz]='O';
			
			//Calls function to bring the board
			board(tictactoe);
			
			//Checks to see if any wins of three in a row 
			wincondition(tictactoe,win,win2);
			
			//adding one to tie
			tie++;
	 	} 
	
		//Asking user where they want to place it if they havent won	
		if ((win==0) && (win2==0) && (tie<9))
		{
			//Asking the user for the position
			do{
			cout<<endl<<player2<<" what position (A#) (B#)--> ";
			cin>>vert>>horz;
			}
			//Loops if the user enters a position not valid, or not filled with an empty space
			while (tictactoe[vert][horz]!=' ');
			
			//Fills the position with an X
			tictactoe[vert][horz]='X';
			
			//Calling to the board function
			board(tictactoe);
			
			//Calling to the win condition function to check if any player wins
			wincondition(tictactoe,win,win2);
			
			//Adding one to tie
			tie++;
		}
		//New line
		cout<<endl;	
		//System pause screen	
		system("Pause");	
		
		//If win is equal to one
		if (win==1)
		{
			//Add one to win counter
			wincounter++;
			
			//Outputting player 1 is the winner
			cout<<player1<<" is the Winner!";
			
			//Outputting the score
			cout<<endl<<"Score\n"<<player1<<" wins:"<<wincounter<<endl<<player2<<" wins:"<<wincounter2;
			
			//Asking user if they want to play again
			cout<<endl<<"Would you like to play again?";
			cin>>response2;
			
			//Getting the length of the word
			length=response2.length();
			
			//Loop to uppercasing the word
			for (int i=0;i<length;i++)
			{
				//Uppercasing the word
				response2[i]=toupper(response2[i]);
			}
			//Adding one to reccuring
			reccuring++;
		}
		//If win2 is equal to one
		else if (win2==1)
		{
			//Add one to wincounter2
			wincounter2++;
			
			//Outputting player2 is the winner
			cout<<player2<<" is the Winner!";
			
			//Outputing the scores
			cout<<endl<<"Score\n"<<player1<<" wins:"<<wincounter<<endl<<player2<<" wins:"<<wincounter2;
			
			//Asking the user wants to play again
			cout<<endl<<"Would you like to play again?";
			cin>>response2;
			
			//Getting the length of the response
			length=response2.length();
			
			//Loop to uppercasing the letters
			for (int i=0;i<length;i++)
			{
				//Uppercasing the letters
				response2[i]=toupper(response2[i]);
			}
			//Add one to reccuring
			reccuring++;
		}
		//If tie is equal to nine
		else if (tie==9)
		{
			//Outputting tie game
			cout<<"\nTie Game";
			//Outputting scores
			cout<<endl<<"Score\n"<<player1<<" wins:"<<wincounter<<endl<<"Computer wins:"<<wincounter2;
			//Asking if they want to play again
			cout<<endl<<"Would you like to play again?";
			cin>>response2;
			//Add one to reccuring
			reccuring++;
			length=response2.length();
			//Loops for how long the length
			for (int i=0;i<length;i++)
			{
				//Sets all the letters in response2 is all uppercase
				response2[i]=toupper(response2[i]);
			}
		} 			
	}
	//Telling the user thanks for playing the game
	cout<<"Thanks for playing =)";
}
//Declaring functions
//Board of tictactoe
void board(char tictactoe[][3])
{
	//System clear screen
	system ("cls");
	//Outputting the board to the screen
	cout<<"     B0      B1     B2";
	cout<<"\n  |\t |\t |\t|";
	//Outputs the first row 
	cout<<"\nA0|  "<<tictactoe[0][0]<<"   |   "<<tictactoe[0][1]<<"   |   "<<tictactoe[0][2]<<"  |";
	cout<<"\n  |\t |\t |\t|";
	cout<<endl<<"---------------------------";
	cout<<"\n  |\t |\t |\t|";
	//Outputs the 2nd row
	cout<<"\nA1|  "<<tictactoe[1][0]<<"   |   "<<tictactoe[1][1]<<"   |   "<<tictactoe[1][2]<<"  |";
	cout<<"\n  |\t |\t |\t|";
	cout<<endl<<"---------------------------";
	cout<<"\n  |\t |\t |\t|";
	//Outputs the 3rd row
	cout<<"\nA2|  "<<tictactoe[2][0]<<"   |   "<<tictactoe[2][1]<<"   |   "<<tictactoe[2][2]<<"  |";
	cout<<"\n  |\t |\t |\t|";
}
//Checking if anyone wins
void wincondition(char tictactoe[][3],int &win, int &win2)
{
	//Checking if 3 o's are in row 0
	if ((tictactoe[0][0]=='O') && (tictactoe[0][1]=='O') && (tictactoe[0][2]=='O'))
	{
		//Add one to win
		win++;
	}
	//Checking if 3 o's are in row 1
	else if ((tictactoe[1][0]=='O') && (tictactoe[1][1]=='O') && (tictactoe[1][2]=='O'))
	{
		//Add one to win
		win++;
	}
	//Checking if 3 o's are in row 2
	else if ((tictactoe[2][0]=='O') && (tictactoe[2][1]=='O') && (tictactoe[2][2]=='O'))
	{
		//Add one to win2
		win++;
	}
	//Checking if 3 o's are in column 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[1][0]=='O') && (tictactoe[2][0]=='O'))
	{
		//Add one to win2
		win++;
	}
	//Checking if 3 o's are in column 1
	else if ((tictactoe[0][1]=='O') && (tictactoe[1][1]=='O') && (tictactoe[2][1]=='O'))
	{
		//Add one to win2
		win++;
	}
	//Checking if 3 o's are in column 2
	else if ((tictactoe[0][2]=='O') && (tictactoe[1][2]=='O') && (tictactoe[2][2]=='O'))
	{
		//Add one to win2
		win++;
	}
	//Checking if 3 o's are in a diagonal
	else if ((tictactoe[0][0]=='O') && (tictactoe[1][1]=='O') && (tictactoe[2][2]=='O'))
	{
		//Add one to win2
		win++;
	}
	//Checking if 3 o's are in the other diagonal
	else if ((tictactoe[0][2]=='O') && (tictactoe[1][1]=='O') && (tictactoe[2][0]=='O'))
	{
		//Add one to win
		win++;
	}
	//Checking if 3 x's are in row 0
	if ((tictactoe[0][0]=='X') && (tictactoe[0][1]=='X') && (tictactoe[2][0]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are in row 1
	else if ((tictactoe[1][0]=='X') && (tictactoe[1][1]=='X') && (tictactoe[1][2]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are in row 2
	else if ((tictactoe[2][0]=='X') && (tictactoe[2][1]=='X') && (tictactoe[2][2]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are in column 0
	else if ((tictactoe[0][0]=='X') && (tictactoe[1][0]=='X') && (tictactoe[2][0]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are in column 1
	else if ((tictactoe[0][1]=='X') && (tictactoe[1][1]=='X') && (tictactoe[2][1]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are in column 2
	else if ((tictactoe[0][2]=='X') && (tictactoe[1][2]=='X') && (tictactoe[2][2]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are in a diagonal
	else if ((tictactoe[0][0]=='X') && (tictactoe[1][1]=='X') && (tictactoe[2][2]=='X'))
	{
		//Add one to win2
		win2++;
	}
	//Checking if 3 x's are another diagonal
	else if ((tictactoe[0][2]=='X') && (tictactoe[1][1]=='X') && (tictactoe[2][0]=='X'))
	{
		//Add one to win2
		win2++;
	}
}
//Computer choice 
int computerpos(int randnum,char tictactoe[][3],int compexit)
{	
	//Getting a random number from 0 - 9
	randnum=(rand() % 10);
	//When two X are touching and the third position is an empty space and compexit equals 0
	if ((tictactoe[0][0]=='X') && (tictactoe[0][1]=='X') && (tictactoe[0][2]==' '))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[1][0]=='X') && (tictactoe[1][1]=='X') && (tictactoe[1][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='X') && (tictactoe[2][1]=='X') && (tictactoe[2][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][1]=='X') && (tictactoe[0][2]=='X') && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[1][1]=='X') && (tictactoe[1][2]=='X') && (tictactoe[1][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][1]=='X') && (tictactoe[2][2]=='X') && (tictactoe[2][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//Columns
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='X') && (tictactoe[1][0]=='X') && (tictactoe[2][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][1]=='X') && (tictactoe[1][1]=='X') && (tictactoe[2][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][1]='X';
		//Adds one to comp exit
		compexit++;
	}	
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='X') && (tictactoe[1][2]=='X') && (tictactoe[2][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='X') && (tictactoe[1][0]=='X') && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][1]=='X') && (tictactoe[1][1]=='X') && (tictactoe[0][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][2]=='X') && (tictactoe[1][2]=='X') && (tictactoe[0][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='X') && (tictactoe[1][1]=='X') && (tictactoe[2][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='X') && (tictactoe[1][1]=='X') && (tictactoe[2][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='X') && (tictactoe[1][1]=='X') && (tictactoe[0][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][2]=='X') && (tictactoe[1][1]=='X') && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='X') && (tictactoe[0][2]=='X') && (tictactoe[0][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[1][0]=='X') && (tictactoe[1][2]=='X') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='X') && (tictactoe[2][2]=='X') && (tictactoe[2][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='X') && (tictactoe[2][0]=='X') && (tictactoe[1][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][1]=='X') && (tictactoe[2][1]=='X') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='X') && (tictactoe[2][2]=='X') && (tictactoe[1][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='X') && (tictactoe[2][0]=='X') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two X are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='X') && (tictactoe[2][0]=='X') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[0][1]=='O') && (tictactoe[0][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[1][0]=='O') && (tictactoe[1][1]=='O') && (tictactoe[1][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='O') && (tictactoe[2][1]=='O') && (tictactoe[2][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][1]=='O') && (tictactoe[0][2]=='O') && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[1][1]=='O') && (tictactoe[1][2]=='O') && (tictactoe[1][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][1]=='O') && (tictactoe[2][2]=='O') && (tictactoe[2][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//Columns
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[1][0]=='O') && (tictactoe[2][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][1]=='O') && (tictactoe[1][1]=='O') && (tictactoe[2][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][1]='X';
		//Adds one to comp exit
		compexit++;
	}	
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='O') && (tictactoe[1][2]=='O') && (tictactoe[2][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	else if ((tictactoe[2][0]=='O') && (tictactoe[1][0]=='O') && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][1]=='O') && (tictactoe[1][1]=='O') && (tictactoe[0][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][2]=='O') && (tictactoe[1][2]=='O') && (tictactoe[0][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[1][1]=='O') && (tictactoe[2][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='O') && (tictactoe[1][1]=='O') && (tictactoe[2][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='O') && (tictactoe[1][1]=='O') && (tictactoe[0][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][2]=='O') && (tictactoe[1][1]=='O') && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[0][2]=='O') && (tictactoe[0][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[1][0]=='O') && (tictactoe[1][2]=='O') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[2][0]=='O') && (tictactoe[2][2]=='O') && (tictactoe[2][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[2][0]=='O') && (tictactoe[1][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][0]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][1]=='O') && (tictactoe[2][1]=='O') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='O') && (tictactoe[2][2]=='O') && (tictactoe[1][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][2]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][0]=='O') && (tictactoe[2][0]=='O') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//When two O are touching and the third position is an empty space and compexit equals 0
	else if ((tictactoe[0][2]=='O') && (tictactoe[2][0]=='O') && (tictactoe[1][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adds one to comp exit
		compexit++;
	}
	//checking if the number is 0 and theres an empty space to insert an x
	else if ((randnum==0) && (tictactoe[0][0]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][0]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 1 and theres an empty space to insert an x
	else if ((randnum==1) && (tictactoe[0][1]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][1]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 2 and theres an empty space to insert an x
	else if ((randnum==2) && (tictactoe[0][2]==' ') && (compexit==0))
	{
		//Fills position with an X
		tictactoe[0][2]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 3 and theres an empty space to insert an x
	else if ((randnum==3) && (tictactoe[1][0]==' ')&& (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][0]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 4 and theres an empty space to insert an x
	else if ((randnum==4) && (tictactoe[1][1]==' ')&& (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][1]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 5 and theres an empty space to insert an x
	else if ((randnum==5) && (tictactoe[1][2]==' ')&& (compexit==0))
	{
		//Fills position with an X
		tictactoe[1][2]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 6 and theres an empty space to insert an x
	else if ((randnum==6) && (tictactoe[2][0]==' ')&& (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][0]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 7 and theres an empty space to insert an x
	else if ((randnum==7) && (tictactoe[2][1]==' ')&& (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][1]='X';
		//Adding one to compexit
		compexit++;
	}
	//checking if the number is 8 and theres an empty space to insert an x
	else if ((randnum==8) && (tictactoe[2][2]==' ')&& (compexit==0))
	{
		//Fills position with an X
		tictactoe[2][2]='X';
		//Adding one to compexit
		compexit++;
	}
	//When compexit equals 1
	if (compexit==1)
	{
		//Return compexit
		return (compexit);
	}
}
//Guessing game 
void guessinggame()
{
	//Declaring function
	void user1(int number,int MyArray[][1000],int &count,int &count2,int &count3);

	//Declaring variables
	string enter;
	int length,count,count2,count3;
	
	//Clearing screen
	system("cls");	
	//Outputting guessing game in ascii art
	cout<<" _____                      _                _____";                         
	cout<<endl<<"/ ____|                    (_)              / ____|";                        
	cout<<endl<<"| |  __ _   _  ___  ___ ___ _ _ __   __ _  | |  __  __ _ _ __ ___   ___ ";
	cout<<endl<<"| | |_ | | | |/ _ \\/ __/ __| | '_ \\ / _` | | | |_ |/ _` | '_ ` _ \\ / _ \\"; 
	cout<<endl<<"| |__| | |_| |  __/\\__ \\__\\| | | |   (_| | | |  | | (_| | | | | | |  __/"; 
	cout<<endl<<"\\_____|\\__,_|\\___||___/___/|_|_| |_|\\__, |  \\_____|\\__,_|_| |_| |_|\\___|";  
	cout<<endl<<"                                     __/ |                            ";  
	cout<<endl<<"                                    |____/ ";
	
	//Outputting a guy thinking of a number in ascii art
	cout<<endl<<"            .-\"\"-.--.--.";	                        
	cout<<endl<<"           (   what    )";                           
	cout<<endl<<"            (  number  )";                            
	cout<<endl<<"             '--'--'--'";                             
	cout<<endl<<"               ()";                               
	cout<<endl<<"/^^^^^^^       O";
	cout<<endl<<"|  (')')   o";                
	cout<<endl<<"C     _)";                
	cout<<endl<<"\\   _|";                 
	cout<<endl<<"\\__/";                  
	cout<<endl<<"<___Y>";              
	cout<<endl<<"/  \\ :\\\\";                
	cout<<endl<<"/   | :|\\";              
	cout<<endl<<"|___| :|/\\";               
	cout<<endl<<"| |   :|\\ \\";                
	cout<<endl<<"\\ \\   :| \\ \\_";                
	cout<<endl<<"\\ \\==L|  \\\\\\";                 
	cout<<endl<<"///` ||";                 
	cout<<endl<<" |   ||";                  
	cout<<endl<<" |   ||";                  
	cout<<endl<<" |   ||";                  
	cout<<endl<<" |   ||";                  
	cout<<endl<<" |   ||";                  
	cout<<endl<<" |   ||";                  
	cout<<endl<<" [___]]";                  
	cout<<endl<<" (____))";          
	
	//Asking if the user wants to play the guessing game
	cout<<"\n\nWould you like to play the 3 player guessing game? ";
	cin>>enter;
	
	//Length of the word entered
	length=enter.length();	
	
	//Looping when i is less than length
	for (int i=0;i<length;i++)
	{
		//Uppercasing each letter
		enter[i]=toupper(enter[i]);
	}
	
	//Loops until enter is not a synonym of yes
	while ((enter=="YES") || (enter=="YEAH") || (enter=="SURE"))
	{
		//Declaring variables
		int number,MyArray[3][1000];
		
		//Bringing in random number
		srand(time(NULL));
		
		//Generating random number
		number=(rand() %1000) + 1;
		
		//Calling to function
		user1(number,MyArray,count,count2,count3);
		
		cout<<endl<<"Would you like to play again? ";
		cin>>enter;
		
		for (int i=0;i<length;i++)
		{
			//Uppercasing each letter
			enter[i]=toupper(enter[i]);
		}
	}
}
//Guessing game part
void user1(int number,int MyArray[][1000],int &count,int &count2,int &count3)
{
	//Declaring function
	void winner(int count,int count2,int count3);
	//System clear screen
	system ("cls");
	//Declaring variable
	int guess;
	count=-1;
	//Loops until the guess is the same as the number
	while (number!=guess)
	{
		//counter
		count++;
		//Outputting guesses
		cout<<"Guesses:";
		//Loop amount of times based on guesses
		for (int i=0;i<count;i++)
		{
			//Output guesses and comma
			cout<<MyArray[0][i]<<",";	
		}
		//Asking the user for the guess
		cout<<"\nUser #1, Please enter your guess from 1 to 1000--> ";
		cin>>guess;
		//Storing guess in the array
		MyArray[0][count]=guess;
		//Tell the user if their guess is too high, low or correct
		if (guess>number)
		{
			//Outputting your guess is too high
			cout<<"Your guess is too high"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
		//When guess is less than number
		else if (guess<number)
		{
			//Outputting the number is too low
			cout<<"Your guess is too low"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
		//When guess is equal to number
		else
		{
			//Outputting they got the number correct
			cout<<"You got it correct"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
	}
	//Outputting guesses
	cout<<"Guesses:";
	//Loop amount of times based on guesses
	for (int i=0;i<count;i++)
	{
		//Output guesses and comma
		cout<<MyArray[0][i]<<",";
		//When i is equal to count minus 1
		if (i==count-1)
		{
			//Output guesses
			cout<<MyArray[0][i+1];
		}	
	}
	//If they guess correctly on their girst try, outputs their guess
	if (count==0)
	{
		//Output guesses
		cout<<MyArray[0][0];
	}
	//New line
	cout<<endl;
	//Pause screen
	system("pause");
	//Clear screen
	system ("cls");

	//User number 2
	//declaring variables
	count2=-1;
	guess=0;
	//Loops until number doesnt equal guess
	while (number!=guess)
	{
		//Add one to count2
		count2++;
		//Output guesses
		cout<<"Guesses:";
		//Loop amount of times based on guesses
		for (int i=0;i<count2;i++)
		{
			//Output guesses and comma
			cout<<MyArray[0][i]<<",";	
		}
		//Asking user to enter a number from 1 to 1000
		cout<<"\nUser #2, Please enter your guess 1 to 1000--> ";
		cin>>guess;
		//Storing guess in the array 
		MyArray[1][count2]=guess;
		//if guess is bigger than the number
		if (guess>number)
		{
			//Outputting your guess is too high
			cout<<"Your guess is too high"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
		//When guess is less than number
		else if (guess<number)
		{
			//Outputting the number is too low
			cout<<"Your guess is too low"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
		//When guess is equal to number
		else
		{
			//Outputting they got the number correct
			cout<<"You got it correct"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
	}
	//Outputting guesses
	cout<<"Guesses:";
	//Looping when i is less than count 2
	for (int i=0;i<count2;i++)
	{
		//Outputting the guess followed by comma
		cout<<MyArray[1][i]<<",";
		//When i is less than count2-1
		if (i==count2-1)
		{
			//Outputs the guess
			cout<<MyArray[1][i+1];
		}
	}
	//When count2 is equal to 0
	if (count2==0)
	{
		//Outputs the guess
		cout<<MyArray[1][0];
	}
	//New line
	cout<<endl;
	//System pause screen
	system("pause");
	//System clear screen
	system ("cls");
	
	//User number 3
	//Redeclaring variables
	count3=-1;
	guess=0;
	//Loops until number doesnt equal guess
	while (number!=guess)
	{
		//Adding one to count3
		count3++;
		cout<<"Guesses:";
		//Loop amount of times based on guesses
		for (int i=0;i<count3;i++)
		{
			//Output guesses and comma
			cout<<MyArray[0][i]<<",";	
		}
		//Asking user for the guess 
		cout<<endl<<"User #3, Please enter your guess 1 to 1000--> ";
		cin>>guess;
		//Storing guess
		MyArray[2][count3]=guess;
		//if guess is bigger than the number
		if (guess>number)
		{
			//Outputting your guess is too high
			cout<<"Your guess is too high"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
		//When guess is less than number
		else if (guess<number)
		{
			//Outputting the number is too low
			cout<<"Your guess is too low"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
		//When guess is equal to number
		else
		{
			//Outputting they got the number correct
			cout<<"You got it correct"<<endl;
			//System pause screen
			system("pause");
			//System clear screen
			system("cls");
		}
	}
	//Outputting guess
	cout<<"Guesses:";
	//Going through the array and outputting to the user the guesses
	for (int i=0;i<count3;i++)
	{
		//Outputting guess followed by a comma
		cout<<MyArray[2][i]<<",";
		//If the count3 is subtracted by one
		if (i==count3-1)
		{
			//Output the guess with no comma
			cout<<MyArray[2][i+1];
		}
	}
	//If count3 is equal to 0
	if (count3==0)
	{
		//Outputs the guess
		cout<<MyArray[2][0];
	}
	//New line
	cout<<endl;
	//Pausing screen
	system("pause");
	//Clearing screen
	system ("cls");
	//Outputting user 1 guesses
	cout<<"User #1"<<endl<<"Guesses:";
	//Looping when i is less than count
	for (int i=0;i<count;i++)
	{
		//outputs the guess followed by comma
		cout<<MyArray[0][i]<<",";
		//When is is equal to count minus one
		if (i==count-1)
		{
			//Outputs guess
			cout<<MyArray[0][i+1];
		}
	}
	//When count is equal to 0
	if (count==0)
	{
		//Outputs the guess
		cout<<MyArray[0][0];
	}
	//Outputting user 2 guesses
	cout<<endl<<"User #2"<<endl<<"Guesses:";
	//Looping until i is equal to count2
	for (int i=0;i<count2;i++)
	{
		//Outputting guess and comma
		cout<<MyArray[1][i]<<",";
		//When i is equal to count2-1
		if (i==count2-1)
		{
			//Outputs guesses
			cout<<MyArray[1][i+1];
		}
	}
	//When count2 is equal to 0	
	if (count2==0)
	{
		//Outputs guess
		cout<<MyArray[1][0];
	}
	//Outputting user 3 guesses
	cout<<endl<<"User #3"<<endl<<"Guesses:";
	//Loop until i is equal to count3
	for (int i=0;i<count3;i++)
	{
		//Outputs guess followed by comma
		cout<<MyArray[2][i]<<",";
		//When i is equal to count3 minus 1
		if (i==count3-1)
		{
			//Outputs guess
			cout<<MyArray[2][i+1];
		}
	}
	//When count 3 is equal to 0
	if (count3==0)
	{
		//Outputs guess
		cout<<MyArray[2][0];
	}
	//Calls to the winner function	
	winner(count,count2,count3);	
}
//Determines the winner of the guessing game
void winner(int count,int count2,int count3)
{
	//Stating which user won
	if ((count<count2) && (count<count3))
	{
		//Outputting user 1 had fewest guesses
		cout<<endl<<"User #1 had the fewest amount of guesses";
	}
	//When count 2 is less than count and count 2 is less than count3
	else if ((count2<count) && (count2<count3))
	{
		//Outputing user 2 had the fewest guesses
		cout<<endl<<"User #2 had the fewest amount of guesses";
	}
	//When count3 is less than count and count3 is less than count2
	else if ((count3<count) && (count3<count2))
	{
		//Outputing user 3 had the fewest guesses
		cout<<endl<<"User #3 had the fewest amount of guesses";
	}
	//When count3 is less than count and count 3 is equal to count2
	else if ((count3<count) && (count3==count2))
	{
		//Outputting user 3 and 2 had the fewest guesses
		cout<<endl<<"User #3 and 2 had the fewest amount of guesses";	
	}
	//When count3 is equal to count and count3 is less than count2
	else if ((count3==count) && (count3<count2))
	{
		//Outputting user 3 and 1 had the fewest guesses
		cout<<endl<<"User #3 and 1 had the fewest amount of guesses";	
	}
	//when count 2 is equal to count 1 and count 2 is less than count 3
	else if ((count2==count) && (count2<count3))
	{
		//Outputting users 1 and 2 had the fewest guesses
		cout<<endl<<"User #2 and 1 had the fewest amount of guesses";	
	}
	//All 3 users had the same amount of guesses
	else 
	{
		//Outputing they all had the same amount of guesses
		cout<<endl<<"All had the same amount of guesses";	
	}
}

//Maze game
void Mazegame()
{
	/******************************************************************************************
	*	Brayden Mills											                              *
	*	June 5th 2018											                              *												
	*	Purpose: Summative Maze Game                                                          *                       
	*   Data Dictionary: RandXGen....function to randomly generate location of x(finish)      *           
	*					 GridCreator....function to create the grid to play on                *
	*					 BombCreator....function to randomly generate all the bombs           *
	*					 Moves....function to move player across grid based on their input    *
	*					 BombChecker....function to check if user hit the bombs placed around *
	*					 WinChecker....function to check to see if user won game              *
	*                    i,j....hold counts for the for loops                                 *
	*                    x,y....hold location of user (>) on grid                             *
	*                    num,num2....holds randomly generated location of x on grid           *
	*                    Bombcount....count for the number of revives user has left           *
	*                    Incorrect....count for the number of questions user got wrong        * 
	*                    wincount....count for the number of user wins                        *
	*                    name....holds name entered by user                                   *
	*                    BombGrid....Array that holds all the positions of the bombs for game *
	*                    Grid....Array that holds and outputs the design of grid for user     *
	*                    bombx,bomby....holds position of the bombs before their put in array *
	*                    move....holds the character entered by user on where they wanna move *
	*                    Qnum,Qnum2....holds two random numbers for math problem              *
	*                    Qans,Qans2....holds user ans to math problem and the actual answer   *
	*                    sign....holds random number generated to determine type of problem   *                     
	*   Dev-C++ 5.11                                                                          *
	*															                              *
	******************************************************************************************/
	//Declaring Functions
	void RandXGen(string Grid[][12],int&num,int&num2);
	void GridCreator(string Grid[][12]);
	void BombCreator(string BombGrid[][12],int num,int num2);
	void Moves(string Grid[][12],int&x,int&y);
	void BombChecker(string BombGrid[][12],int x,int y,int&Bombcount,int&Incorrect);
	int WinChecker(string Grid[][12],int x,int y,int&wincount,int num,int num2);

	
	//declaring variables
    int i,j,x=10,y=10,num,num2,Bombcount=3,Incorrect=0,wincount=0;
    string name;
	
	//Changes Background and text color of program
	system("color 2F");
	
	
	//Declaring and setting arrays
	string Grid[12][12]={{"-","-","-","-","-","-","-","-","-","-","-","-"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"-","-","-","-","-","-","-","-","-","-","-","-"}};
	string BombGrid[12][12]={{"-","-","-","-","-","-","-","-","-","-","-","-"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"|","*","*","*","*","*","*","*","*","*","*","|"},{"-","-","-","-","-","-","-","-","-","-","-","-"}};
    Grid[10][10]=">";
    
    //welcomes user to game 
    cout<<"\n Welcome to ";
    
    //outputs game name
    cout<<"\n _________ ___   ___ ________   ___________ ________ _________  ________";
    cout<<"\n |__   __| | |   | | |  ____|   | ___ ___ | | ____ | |___    /  |  ____|"; 
    cout<<"\n    | |    | |___| | | |____    | | | | | | | |__| |     /  /   | |____ ";
    cout<<"\n    | |    |  ___  | |  ____|   | | | | | | | ____ |    /  /    |  ____|";
    cout<<"\n    | |    | |   | | | |____    | | |_| | | | |  | |   /  /___  | |____ ";
    cout<<"\n    |_|    |_|   |_| |______|   |_|     |_| |_|  |_|  /_______| |______|";

	//ask user for name
	cout<<"\n Enter your name to begin-> ";
	//gets user name and holds it in var name
	cin>>name;
	
	//clears screen
	system("cls");
	
	//tells user the objective of game
	cout<<"\n Hey "<<name;
	cout<<"\n The goal of the game is to get to the x without hitting the 15 bombs\n placed around the grid, you have a chance to revive for the first 3\n good luck (:\n\n\n\n\n\n\n";
	
	//pauses screen well user reads instructions
	system("pause");
	
	//clears screen
	system("cls");
	
	//Calling function to generate a random position for x
    RandXGen(Grid,num,num2);
    
	//Calling function to generate bombs
    BombCreator(BombGrid,num,num2);	
    
    //loops as long as user doesn't get question wrong, wins or hits to many bombs
    while((Bombcount!=-1)&&(Incorrect!=1)&&(wincount!=1))
    {
    	//clears screen
    	system("cls");
    	
	    //Calling function to output grid to screen
	    GridCreator(Grid);
	    
	    //Calling function to move user
	    Moves(Grid,x,y);
	    
	    //Calling function to check and see if user landed on a bomb
	    BombChecker(BombGrid,x,y,Bombcount,Incorrect);
	    
	    //checks to see if you won or not 
	    WinChecker(Grid,x,y,wincount,num,num2);                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
    }
    //clears screen
    system("cls");
}

//Generates the location of X on the Grid
void RandXGen(string Grid[][12],int&num,int&num2)
{
	
	//gets random seeded numbers
	srand (time(NULL));
	
	//Generates a Random num between 1 and 8
	num = rand() % 8 + 1;
	//Generates a Random num between 1 and 10
    num2 = rand() % 10 + 1;
    
    //Sets x equal to the postion on the grid based on the two random numbers generated 
    Grid[num][num2]= "X";
		
}
	
//Outputs grid 
void GridCreator(string Grid[][12])
{
	//Declaring variables
	int i,j;
	
	//Tells user what their controlling
	cout<<"\n Your character is the > at the bottom right of the grid ";
	
	//skips to next line and tabs over 
	cout<<"\n\t";
	
	//loops to output 2d array which is the graph
	for(j=0;j<12;j++)
	{
		//loops to output 2d array which is the graph
		for(i=0;i<12;i++)
		{
			//outputs 2d array which is graph to screen
			cout<<Grid[j][i];
		}
		//skips to next line and tabs over
		cout<<"\n\t";
	}	
}
	
//Creates bomb positions and sets that position equal to B
void BombCreator(string BombGrid[][12],int num,int num2)
{
	//Declaring Variables
	int bombx,bomby,i;
	
	//gets random seeded numbers
	srand (time(NULL));
	
	//loops till 15 bombs are generated
	for(i=0;i<=15;i++)
	{
		//Generates a Random num between 1 and 10
		bomby = rand() % 10 + 1;
		//Generates a Random num between 1 and 10
	    bombx = rand() % 10 + 1;
	    
	    //checks to see if a bomb is generated on the starting place of user or x and if it is it regenerates the numbers until they don't equal it
	    while ((bomby==10)&&(bombx==10)&&(bomby==num)&&(bombx==num2))
	    {
		    //Generates a Random num between 1 and 10
			bomby = rand() % 10 + 1;
			//Generates a Random num between 1 and 10
		    bombx = rand() % 10 + 1;
		}

		//Sets B equal to the postion on the grid based on the two random numbers generated 
		BombGrid[bomby][bombx]= "B";
	
	}
}
	
//Moves user on the grid depending on the letter they enter
void Moves(string Grid[][12],int&x,int&y)
{
	//Declaring variables
	char move;
	
	//tells user what letter to enter to go in each direction on the grid
	cout<<"\n To Move Enter W to go up, S to go down, A to go right and D to go left. ";
	//gets user move
    cin>>move;
    
    //makes letter entered by user uppercase just in case it isn't so it works in case statement
    move= toupper(move);
    
    //states what to do when move equals each letter
    switch(move)
	{
		//states what to do when move is W
		case('W'):
		   //changes previous place of user to equal *
		   Grid[y][x]="*";
		   //adds 1 to y to move up 1 space on grid
		   y--;
		   //moves user up 1 space on grid
		   Grid[y][x]=">";
		   //stops the switch and signifies the end of that case
		   break;
		//states what to do when move is S
		case('S'):
		   //changes previous place of user to equal *
		   Grid[y][x]="*";
		   //subtracts 1 from y to move down 1 space on grid
		   y++;
		   //moves user down 1 space on grid
		   Grid[y][x]=">";
		   //stops the switch and signifies the end of that case
		   break;
		//states what to do when move is A
		case('A'):
		   //changes previous place of user to equal *
		   Grid[y][x]="*";
		   //subtracts 1 from x to move left 1 space on grid
		   x--;
		   //moves user left 1 space on grid
		   Grid[y][x]=">";
		   //stops the switch and signifies the end of that case
		   break;
		//states what to do when move is D
		case('D'):
		   //changes previous place of user to equal *
		   Grid[y][x]="*";
		   //adds 1 to x to move left 1 space on grid
		   x++;
		   //moves user right 1 space on grid
		   Grid[y][x]=">";
		   //stops the switch and signifies the end of that case
		   break;
		//states what to do when move is anything other than W,S,A,D
		default:
			//says to user that their entry was invalid
			cout<<"invalid";
			//stops the switch and signifies the end of that case
			break;
	}  
}

//Checks to see if user landed on a bomb and how many they've landed on
void BombChecker(string BombGrid[][12],int x,int y,int&Bombcount,int&Incorrect)
{
	//Declaring variables
	int Qnum,Qnum2,sign;
	float Qans,Qans2;
	
	//checks to see if user has had 3 revives yet and if they have then output you lose
	if (Bombcount==0)
	{
		//tells user they lose
		cout<<"\n Good game you hit to many bombs, you lose";
		//pause screen
		system("pause");
		//takes 1 away from bombcount
		Bombcount--;
	}
	//checks to see if you landed on a bomb and if you did you answer a question to revive
	else if (BombGrid[x][y]=="B")
	{
		//tells you you landed on a bomb
		cout<<"\n You hit a Bomb ";
		//pause screen
		system("pause");
		//takes 1 away from bombcount
		Bombcount--;
		//tells user what to do
		cout<<"\n To continue answer the following math question right. ";
		
		//gets random seeded numbers
	    srand (time(NULL));
	    //Generates a Random num between 1 and 10
		Qnum = rand() % 10 + 1;
		//Generates a Random num between 1 and Qnum
		Qnum2 = rand() % Qnum+ 1;
		//Generates a Random num between 1 and 4
		sign = rand() % 4 + 1;
		
        //Decides what kind of math questions to generate
        //generates multiplication questions when sign equals 1
		if (sign==1)
		{
			//asks user answer to Qnum x Qnum2
		    cout<<"\n What's "<<Qnum<<"x"<<Qnum2<<"->";	
		    //calculates answer
		    Qans= Qnum*Qnum2;
		    //gets user answer
		    cin>>Qans2;
		    
		    //Checks to see if userans is the same as the actual answer
		    if(Qans2==Qans)
		    {
		    	//outputs user is right and the number of revives they have left
		    	cout<<"\n Your correct, you have "<<Bombcount<<" more chances to revive ";
		    	//pause screen
		    	system("pause");
			}
			//tells what to do if user got answer wrong
			else
			{
				//outputs to user they got answer wrong and they lost
				cout<<"\n Incorrect, Good Game you lost";
				//pause screen
		    	system("pause");
		    	//adds 1 to incorrect count
				Incorrect++;
			}
		    
		}
		//generates Division questions when sign equals 2
		else if (sign==2)
		{
			//asks user answer to Qnum divided by Qnum2
			cout<<"\n What's "<<Qnum<<"/"<<Qnum2<<"->";	
			//calculates answer
		    Qans= Qnum/Qnum2;
		    //gets user answer
		    cin>>Qans2;
		    
		    //Checks to see if userans is the same as the actual answer
		    if(Qans2==Qans)
		    {
		    	//outputs user is right and the number of revives they have left
		    	cout<<"\n Your correct, you have "<<Bombcount<<" more chances to revive ";
		    	//pause screen
				system("pause");	
			}
			//tells what to do if user got answer wrong
			else
			{
				//outputs to user they got answer wrong and they lost
				cout<<"\n Incorrect, Good Game you lost";
				//pause screen
		    	system("pause");
		    	//adds 1 to incorrect count
				Incorrect++;
			}
		}
		else if(sign==3)
		{
			//asks user answer to Qnum + Qnum2
			cout<<"\n What's "<<Qnum<<"+"<<Qnum2<<"->";
			//calculates answer	
		    Qans= Qnum+Qnum2;
		    //gets user answer
		    cin>>Qans2;
		    
		    //Checks to see if userans is the same as the actual answer
		    if(Qans2==Qans)
		    {
		    	//outputs user is right and the number of revives they have left
		    	cout<<"\n Your correct, you have "<<Bombcount<<" more chances to revive ";
		    	//pause screen
		    	system("pause");
			}
			//tells what to do if user got answer wrong
			else
			{
				//outputs to user they got answer wrong and they lost
				cout<<"\n Incorrect, Good Game you lost";
				//pause screen
		    	system("pause");
		    	//adds 1 to incorrect count
				Incorrect++;
			}
		}
		//generates subtraction questions if it doesn't equal 1,2,3
		else
		{
			//asks user answer to Qnum - Qnum2
			cout<<"\n What's "<<Qnum<<"-"<<Qnum2<<"->";	
			//calculates answer
		    Qans= Qnum-Qnum2;
		    //gets user answer
		    cin>>Qans2;
		    
		    //Checks to see if userans is the same as the actual answer
		    if(Qans2==Qans)
		    {
		    	//outputs user is right and the number of revives they have left
		    	cout<<"\n Your correct, you have "<<Bombcount<<" more chances to revive ";
		    	//pause screen
		    	system("pause");
			}
			//tells what to do if user got answer wrong
			else
			{
				//outputs to user they got answer wrong and they lost
				cout<<"\n Incorrect, Good Game you lost";
				//pause screen
		    	system("pause");
		    	//adds 1 to incorrect count
				Incorrect++;
			}
		}	
		
	}
}

//checks to see if user won 
int WinChecker(string Grid[][12],int x,int y,int&wincount,int num,int num2)
{
	//checks if user position equals the position of x
	if (Grid[y][x]==Grid[num][num2]) 
	{
		//tells user they won
		cout<<"\n You Win, congrats";
		//pause screen
		system("pause");
		//adds 1 to wincount
		wincount++;
		
	}
}

Main Menu.cpp
Displaying Main Menu.cpp.
