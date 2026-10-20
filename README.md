# hamarova.com

Osobný web Ľubice Hamarovej. Jednoduchý Jekyll web bez témy.

## Čo je kde

| Súbor / priečinok | Čo obsahuje |
|---|---|
| `_config.yml` | nastavenia: meno, mesto, e-mail, LinkedIn, fotografia |
| `index.html` | úvodná stránka so všetkými sekciami |
| `_data/expertiza.yml` | tri polia v sekcii Expertíza |
| `_data/profil.yml` | riadky v sekcii Profil (roky a názov) |
| `_posts/` | články (sekcia Texty), každý článok = jeden súbor |
| `texty.html` | stránka so zoznamom všetkých článkov |
| `_layouts/default.html` | spoločná kostra: hlavička s menu a kontaktný pás |
| `_layouts/post.html` | vzhľad stránky s jedným článkom |
| `assets/css/style.css` | farby, písma a rozloženie (farby sú hore v časti „Nastavenia“) |
| `assets/img/` | obrázky a fotografie |
| `_archiv/` | staré stránky (na webe sa nezobrazujú) |
| `.github/workflows/deploy.yml` | automatické zverejnenie po pushnutí do `master` |

## Ako pridať nový článok

1. V priečinku `_posts/` vytvor nový súbor. Názov musí začínať dátumom:
   `RRRR-MM-DD-kratky-nazov.md`, napríklad `2026-01-15-nove-data-o-chudobe.md`.
   V názve súboru nepoužívaj diakritiku ani medzery.
2. Na začiatok súboru napíš toto (medzi dve čiary `---`):

   ```
   ---
   title: "Názov článku s diakritikou"
   typ: Analýza
   ---

   Tu začína text článku. Odseky oddeľ prázdnym riadkom.

   ## Medzinadpis

   Ďalší text. Odkaz sa píše takto: [text odkazu](https://example.com).
   ```

   - `typ` je štítok vpravo (napr. Blog, Analýza, Médiá). Môžeš ho vynechať.
3. Ak je článok uverejnený inde (napr. na SME blogu), stačí pridať riadok s odkazom
   a text nepísať:

   ```
   ---
   title: "Názov článku"
   typ: Blog
   odkaz: https://blog.sme.sk/...
   ---
   ```

4. Ak nepoznáš presný dátum, daj do názvu súboru približný (slúži na zoradenie)
   a pridaj riadok `zobrazit_datum: "2/2022"`. Na webe sa potom ukáže tento text
   namiesto dátumu.

Na úvodnej stránke sa zobrazia tri najnovšie články, na stránke `/texty/` všetky.

## Lokálny náhľad

Raz treba nainštalovať novšie Ruby (to v Macu je príliš staré). Potom stačí:

```
bundle install
bundle exec jekyll serve
```

a otvoriť v prehliadači http://localhost:4000. Náhľad zastavíš klávesmi `Ctrl + C`.
