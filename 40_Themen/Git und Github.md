# Schritte

1. Account bei github.com anlegen [GitHub](https://github.com/)
2. Entsprechende Software für die Arbeitsumgebung (bei uns Windows-PC)
	1. GIT - konsolenbasierte Anwendung um mit Github-Repositories zu kommunizieren
		https://git-scm.com/download/win
	3. Einen Desktop-Client für GIT um komfortabler arbeiten zu können
		https://desktop.github.com/
3. Repository anlegen mit Desktop-Client (enthält auch schon git) - Als Beispiel haben wir unsere Mitschrift genommen - Danach einmal in einem Initial Commit auf github.com raufspielen
4. Nach Änderungen Lokal:
	1. Commit - Mit Betreff und Beschreibung - Änderungen werden im lokalen git-Verzeichnis aufgenommen
	2. Push (Ein oder mehrere Commits) - Änderungen werden auf github.com (o.ä) übermittelt

Lokale Commits (Änderungen) benötigen eine Beschreibung + Betreff:

![[Pasted image 20231114082027.png]]

Wurden lokale Commits getätigt, so sieht das UI von Github Desktop folgendermaßen aus:
- No local changes
- You have xx local commits waiting to be pushed to GitHub

![[Pasted image 20231114081659.png]]

In Obsidian verwenden wir das "Obsidian Git"-Plugin. Dazu muss GIT installiert sein bzw. bei portabler Version der Pfad zur Git-Binary in den Umgebungsvariablen (Lokaler Benutzer - Path-Variable) erfasst sein.