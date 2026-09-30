# God's Eye View internete (Render.com)

Šioje repozitorijoje yra [bilawalsidhu/gods-eye-view](https://github.com/bilawalsidhu/gods-eye-view)
kodas ir `render.yaml` failas, pagal kurį Render.com pats sukompiliuoja ir
paleidžia programą. Į kompiuterį nieko siųstis nereikia.

## Paleidimas (~10 min., vieną kartą)

1. Užeikite į <https://render.com> ir prisijunkite su savo **GitHub** paskyra.
2. Viršuje spauskite **New → Blueprint**.
3. Suteikite Render prieigą prie repozitorijos **Garbana/Gods-eye** ir ją pasirinkite.
   Jei Render leidžia rinktis šaką, pasirinkite tą, kurioje yra šis failas.
4. Render parodys laukelius `CESIUM_ION_TOKEN`, `GOOGLE_MAPS_API_KEY` ir `OPENAI_API_KEY`.
   Juos **galima palikti tuščius**: programa veiks ir be jų.
5. Spauskite **Apply / Deploy**. Pirmas kompiliavimas trunka 5–10 min.
6. Kai būsena taps **Live**, viršuje matysite adresą, pvz.
   `https://gods-eye-xxxx.onrender.com`. Jį atsidarykite bet kurioje naršyklėje, ir telefone.

## Ką verta žinoti

- **Nemokamas planas „užmiega“** po ~15 min. be lankytojų. Kitą kartą atidarius
  svetainę, ji kraunasi ~1 min. Tai normalu.
- **Mygtukas „POWER UP“ programoje debesyje neveiks**: jis sukurtas tik vietiniam
  kompiuteriui. Raktus įveskite Render'e: **jūsų servisas → Environment**,
  tada **Manual Deploy → Deploy latest commit**.
- **Fotorealistinis 3D vaizdas:** nemokamas raktas <https://cesium.com/ion>
  (Access Tokens → numatytasis arba naujas `assets:read` tokenas) → įrašykite
  jį į `CESIUM_ION_TOKEN`. Cesium nustatymuose galima leisti tokeną naudoti tik
  jūsų `onrender.com` adresu.
- **Valdymas balsu:** `OPENAI_API_KEY` (mokamas). Adresas viešas, todėl
  OpenAI svetainėje (Settings → Limits) būtinai nustatykite mėnesio išlaidų limitą.
  Užklausų skaičius vienam lankytojui jau apribotas `render.yaml` faile.
- Kiti neprivalomi raktai (laivai, gaisrai, eismas) aprašyti `.env.example`
  faile. Juos irgi galima pridėti per **Environment**.

## Kaip atnaujinti iki naujausios originalo versijos

Originalus projektas dažnai atnaujinamas. Kai norėsite naujovių, paprašykite
Claude „atnaujink iš upstream“ arba terminale paleiskite:

```bash
git remote add upstream https://github.com/bilawalsidhu/gods-eye-view.git
git pull upstream main
git push
```

Render pastebės naują commit'ą ir pats persidiegs.

## Licencija

Kodas: MIT (žr. `LICENSE`). Kai kurie įdėti duomenys skirti tik nekomerciniam
naudojimui (žr. `DATA_SOURCES.md`). Asmeniniam naudojimui tai netrukdo.
