<h1>
  Hero Section Met P5
</h1>
  In deze test heb ik onderzocht hoe ik een p5 sketch kan inladen op een detailpagina van een project. 
  Daarbij heb ik vooral gekeken of de sketch goed binnen de hero section blijft staan en niet kapot gaat wanneer de pagina responsive wordt.
</p>
<p>
  Tijdens deze test heb ik ook rekening gehouden met performance. 
  De p5 library wordt lokaal ingeladen vanuit de vendor map, zodat de pagina niet afhankelijk is van een externe CDN en de sketch betrouwbaarder kan laden.
</p>
<img width="1512" height="769" alt="performance score" src="https://github.com/user-attachments/assets/1bcd64f1-3f16-48d8-869f-50bf7292e18c" />


<p>
  Ik heb de pagina getest in verschillende browsers (Chrome, Safari en Firefox). 
  In deze browsers blijft de layout werken en wordt de p5 sketch goed ingeladen.
</p>

<p>
  Daarnaast heb ik getest hoe ik de p5 sketch downloadbaar kan maken. 
  Door de sketch-container klikbaar te maken, kan de bezoeker het JavaScript-bestand van de p5 sketch downloaden.
</p>

<h2>
  Grid lay-out
</h2>
<p>
  Voor deze hero section gebruik ik CSS Grid, omdat de layout uit twee duidelijke delen bestaat: 
  links de projectinformatie en rechts de p5 sketch. Grid is hiervoor handig, omdat je makkelijk kolommen 
  kunt maken en die later op kleinere schermen onder elkaar kunt zetten.
</p>
<img width="492" height="39" alt="CSS grid code" src="https://github.com/user-attachments/assets/10abdb59-cfdb-4fea-8a75-fcaa69b434ef" />
<p>
  De eerste kolom is voor de tekst. Met minmax() zorg ik dat deze kolom niet te smal wordt, maar ook niet te veel ruimte inneemt. 
  De tweede kolom gebruikt 1fr, waardoor de p5 sketch automatisch alle overgebleven ruimte krijgt.
</p>

<h2>
  Responsiveness
</h2>

<p> Om de layout responsive te maken, verandert de grid op kleinere schermen naar één kolom:</p>
<img width="283" height="75" alt="Grid CSS" src="https://github.com/user-attachments/assets/e263d164-306a-4750-9070-b7eb079a8d9c" />

<p>De p5 sketch wordt boven de tekst gezet met:</p>
<img width="221" height="72" alt="volgorde grid CSS code" src="https://github.com/user-attachments/assets/30dd491f-34a7-424a-8ec3-13e54ffaa11e" />


<h2>
  P5 inladen
</h2>
<p>
  De p5 sketch wordt geladen door eerst de p5 library te laden en daarna het eigen sketch-bestand:
</p>
<img width="541" height="36" alt="html script p5" src="https://github.com/user-attachments/assets/cf50a4e7-3164-4161-85ea-3fb1a6ef6bac" />
<p>
  De p5 library staat lokaal in de vendor map. Daardoor hoeft de site p5 niet van het internet te downloaden en werkt de sketch betrouwbaarder.
</p>

<p>
  Belangrijk is dat CSS de zichtbare grootte van de sketch bepaalt. 
  De p5 canvas mag nog steeds 1920 x 1080 zijn, maar de container bepaalt hoe groot de sketch op de pagina wordt getoond.
</p>
<img width="212" height="162" alt="max-height CSS code" src="https://github.com/user-attachments/assets/cfed7c09-7866-44e4-8274-eba7f893ee63" />

<p>
  In main.js wordt de canvas die p5 aanmaakt automatisch opgezocht en verplaatst naar de container #project-sketch.
</p>
<img width="484" height="217" alt="p5 javascript code" src="https://github.com/user-attachments/assets/09730c3a-c2cb-41e3-9e2e-682bb78908ec" />



<p>
  Daarna zorgt CSS ervoor dat de canvas het hele vak vult. Met position: absolute, inset: 0, width: 100%, height: 100% en object-fit: cover 
  blijft de canvas netjes binnen de hero. Hierdoor hoef je niet elke p5 sketch apart responsive te maken.
</p>
<img width="252" height="131" alt="canvas CSS code" src="https://github.com/user-attachments/assets/e2c3fafb-c048-4670-821d-5ec5eff9d747" />

<h2>
  P5 code downloaden
</h2>

<p>
  Ik heb de p5 sketch klikbaar gemaakt door een link om de sketch-container heen te zetten. 
  Deze link verwijst direct naar het JavaScript-bestand van de sketch.
</p>
<img width="1068" height="55" alt="html download code" src="https://github.com/user-attachments/assets/d4889b29-1bf9-4ea0-985f-43ebee468ee8" />


<p>
  Omdat ik het download-attribuut gebruik, probeert de browser het bestand te downloaden in plaats van het alleen te openen.
</p>

<p>
  De p5 canvas wordt nog steeds door main.js in de container #project-sketch geplaatst. 
  Omdat #project-sketch binnen de link staat, wordt de hele sketch automatisch klikbaar.
</p>

<p>
  In CSS geef ik de link een hover- en focus-state. Daardoor verschijnt er bij hover of toetsenbordfocus een label met “Download p5 code”. 
  De focus-state is belangrijk voor toegankelijkheid, omdat mensen die met het toetsenbord navigeren dan ook kunnen zien dat de sketch interactief is.
</p>
<img width="270" height="39" alt="CSS downlaod code" src="https://github.com/user-attachments/assets/aee61a3b-095a-4f29-9601-5956e1acdbec" />
<img width="344" height="182" alt="CSS downlaod code focus state" src="https://github.com/user-attachments/assets/21ce549b-3af6-4bc9-8599-79f2a0f1ee90" />



<h2>
  Samengevat
</h2>
<p>Grid bepaalt de layout, CSS bepaalt de grootte van de sketch-container, en main.js verplaatst de p5 canvas naar die container. Daarna zorgt CSS ervoor dat de canvas de container vult zonder de layout kapot te maken.</p>

