# Market-environment

## Uppgift
Detta är en fortsättning av mitt [Förra Projekt](https://github.com/abbsimoga/Enstaka-programerings-projekt/tree/master/Enstaka_programering/StockMarket)

## Bakgrund
I denna fortsättning använde jag mig utav bibloteket **_OpenAI gym_** för att skapa mitt egna *enviornment*. Med bakgrundskunskaper från **_Hands-On Q-Learningwith Python_** och praktiska kunskaper där jag skulle intregrera **_Q-Lerning_** till tre redan skapade gym [*Taxi*, *CartPole* och *Bandit*](https://colab.research.google.com/drive/1RwkDfI0lxFZmXXNk1q88PWA7HQiJjlBL#scrollTo=Ac6y6qG-3kV3). Arbetet började med skapandet av ett eget *Tic Tac Toe* [gym](https://github.com/abbsimoga/TicTacGym) pga enkelheten följd [Medium länk](https://medium.com/@apoddar573/making-your-own-custom-environment-in-gym-c3b65ff8cdaa). Större del av detta arbetet följde min förra kod och exemplerna ovan men även denna [Medium länk](https://towardsdatascience.com/creating-a-custom-openai-gym-environment-for-stock-trading-be532be3910e).

# Förklarning av Q-Learning
## agent, enviornment, state, observation osv

# Grafer

### Avläsande av graf
**_Blåa_** delen av grafen är *agentens* *observation* där den inte invisterar.

**_Gröna_** och **_röda_** markörer tyder på *Short* och *Long* positioner. Förklarning finner du [Här](https://www.investor.gov/introduction-investing/investing-basics/how-stock-markets-work/stock-purchases-and-sales-long-and)

**_Totl Profit_** är multipliken av pengarna agenten började med. *Total Profit* på **2** betyder att agenten dubblade sin insats. Total Profit på **0.5** betyder att agenten förlorade halva sin insats.

**_max_possible_profit_** är den största möjliga multipliken av pengarna agenten började med.

**_Y-Axeln_** är värdet på aktsiens *["Close"]* värde definition finner du [Här](https://www.investopedia.com/terms/c/closingprice.asp)

**_X-Axeln_** är indexen på [csv filerna](https://github.com/abbsimoga/Market-environment/tree/master/Market_environment/datasets). Ett steg i *X-Axeln* är en tidsperiod frammåt. För nerladdad data är tidsperioden i *Dygn*.

## Slutsat1
### Bild 1
Bilden nedan visar på *agentens* observation av marknadens flöde. När observationen *det blå* tydligt tyder på marknadens tillväxt använder *agenten* det till sin vinst se **_Total Profit_** i bild.
![png](docs/Capture3.JPG)

#### Bild 2:1
Bilden visar på när *agentens* observation inte håller sig konsistant under hela miljön. *Agenten* har under observationen lärt sig ett mönster och när det mönstret bryts på grund av aktsiers *"randomness"* vet inte *agenten* vad den ska göra och går i förlust.
![png](docs/Capture1.JPG)

#### ### Bild 2:2
Exempel 2 när liknande ovan händer vid andra aktsier.
![png](docs/Capture2.JPG)

**_Slutsats1:1_** Agenten hittar lätt mönster på tydlig tillväxt och tillbakagång och kan använda det till sin vinst.
**_Slutsats1:2_** Agenten förstår sig inte på glitches i mönstret.

## Slutsats2
### Bild 3
Följande bild visar *medelvärde* av **tio** itterationer på följd som ger ett medel vinst värde på **1.2935849431816784**
![png](docs/Capture7.JPG)

### Bild 4
Kommande bild visar på en körning av [Förra projektets](https://github.com/abbsimoga/Enstaka-programerings-projekt/tree/master/Enstaka_programering/StockMarket) *"AI"* som invisterade på måfå och visade tillväxt och tillbakagång på ca **+-5%**. Exact värde för denna körning = 21772/20000 = **1.0886**.
![png](docs/Capture4.JPG)

### Bild 5
Kommande bild visar på att invistering i aktsier *innom* **_sp500_** leder till *tillväxt* under **längre invisteringar**. Exact värde för **_engångsinvistering_** = 23625/20000 = **1.18125**
![png](docs/Capture6.JPG)

**_Slutsats2:1_** Jämförs dessa två *agenter* finner vi en tydligt förbättring.
**_Slutsats2:2_** Invistering i aktsier *innom* **_sp500_** leder till *tillväxt* under **längre invisteringar** betydligt bättre än min **första** agent.