all: teamName.csv Pld.csv Wins.csv Draws.csv Loss.csv GF.csv GA.csv GD.csv pts.csv table.csv

teamName.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p' | sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/[0-9]*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed 's/+.*//' | sed '/^[[:space:]]*$$/d'  > teamName.csv


Pld.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | egrep '38' > Pld.csv


Wins.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d'  > Wins.csv


Draws.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d' > Draws.csv


Loss.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d' > Loss.csv

GF.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;n;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d' > GF.csv

GA.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;*//' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;n;n;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d' > GA.csv


GD.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;/-/' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;n;n;n;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d' > GD.csv


pts.csv: PremierLeague.txt
	cat PremierLeague.txt | sed -n '/Qualification/,$$p' | sed -n '/Rules for/q;p'| sed 's/<[^>]*>//g' | sed 's/^&#8722//' | sed 's/;/-/' | sed 's/^Q.*//' | sed 's/^R.*//' | sed '/^[[:space:]]*$$/d' | sed -n -e '/[A-Za-z]/ {h;n;n;n;n;n;n;n;n;H;x;p}' | sed 's/[A-Za-z].*//' | sed '/^[[:space:]]*$$/d' > pts.csv


table.csv: 
	paste -d ',' teamName.csv Pld.csv Wins.csv Draws.csv Loss.csv GF.csv GA.csv GD.csv pts.csv > table.csv
