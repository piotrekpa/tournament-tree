tournament-tree
===============


## Jak używać?

### Podstawowa struktura HTML
Każdy poziom (.level) to jeden poziom zawodów. Im mniejszy numer tym wcześniejszy poziom.

	<div class="tournament-tree">
		<section class="level level-1">
			Eliminacje
		</section>
		<section class="level level-2">
			Ćwierć finał
		</section>
		<section class="level level-3">
			Półfinał
		</section>
		<section class="level level-4">
			Finał
		</section>
	</div>


### Struktura meczu
W separatorze można umieszczać np. wyniki meczów `<div class="sep"><span>1:0</span></div>`. Ważne, aby zachować strukturę `div.sep > span`.

	<section class="battle">
		<article class="player player-1">
			<div class="in">
				Player 1
			</div>
		</article>
		<div class="sep"><span>vs.</span></div>
		<article class="player player-2">
			<div class="in">
				Player 2
       </div>
		</article>
	</section>

### CSS
Działa w oparciu o stylusa.
Musimy zaimportować plik tournament_css.styl `@import "tournament_styl.styl"`. Następnie wykonujemy mixin `tournamentTree(ilość poziomów)`.
Gdzie ilość poziomów nie determinuje faktycznie wyświetlanej ilości - jest to przewidywana ilość. Póki co polecaną ilością są 4 poziomy, w innym przypadku trzeba zmienić obrazki.

	@import "tournament_tree.styl"

	body {font-family: Tahoma,Verdana,Arial,sans-serif;}

	tournamentTree(4)

Dodatkowo mamy możemy ustawić takie zmienne jak:

`grid-height` - wysokość jednego elementu z graczem. Ma wpływ na wysokości innych elementów drzewa. Podawana w jednostach nierelatywnych.
`font-size` - wysokość czcionki w elementach takich jak `.player` oraz `.sep`. Podawana w jednostkach nierelatywnych.

