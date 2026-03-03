# About 
Jab hum program run karte time terminal se input dete hain,
aur wo input program ke andar automatically receive hota hai —
usse Command Line Arguments bolte hain. Mtlb program start hone
sa pehle hi data pass kar diya jata hai. 

# *argc* (Argument Counter)
Argument Count ek integer variable hai jo program ko run karte waqt diye gaye total command line arguments ki sankhya batata hai (program name ko include karke).

# *argv* (Argument Vector) 
Argument Vector ek array of strings hai jo command line par diye gaye har argument ko store karta hai.

# Syntax
int main(int argc, char *argv[]) (1st way)

int main(int argc, char **argv) (2nd way) 
