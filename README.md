# UnityCortoSDKTest
Unity Corto SDK Test Repo

Built from '2019.4/staging' branch; Version is '2019.4.28f1 (1381962e9d08) revision 1278358'; Using compiler version '191627012'
OS: 'Windows 10 Home; OS build 19044.1706; Version 2009; 64bit' Language: 'it' Physical Memory: 16259 MB

ITA:

Primo prototipo di utilizzo dell'encoder/decoder Corto in Unity.

https://github.com/cnr-isti-vclab/corto

Per l'utilizzo abbiamo seguito questi passi:

1. Download ed installazione di CMake: https://cmake.org/download/
2. Configurazione per la generazione della solution (in questo caso Window per Visual Studio 2017 Community Edition)
3. Compilazione delle librerie libcorto, utility e decoder per Unity
4. Tramite KenShape abbiamo creato tre semplici mesh 3D poi compresse con l'utility corto

Esempio:

 ./corto -o bottle-potion-texture.corto .\bottle-potion-texture.obj
Encoding time: 1ms
Nvert: 610 Nface: 428
Compressed to: 3248
Ratio: 26.0758%
Bpv: 42.5967

Header: 120 bpv: 0.196721
Coord bpv; 13.7836
Coord q: 0.155065 bits: 7

Normal bpv; 5.12787
Normal q: 512 bits: 10

Uv bpv; 18.4262
Uv q: 0.000244141 bits: 12

Face bpv; 3.04262
TOT M faces: 0.000428 in: 0ms, inf MT/s

5. Creazioen della cartella "Plugins" in cui inserire "cortocodec_unity.dll" (saranno necessari le altre versioni (linux, macosx, etc..) per renderlo cross-platform
6. Creazione cartella "StreamingAssets" dove inserire i file .corto
7. Modifica degli script originali che usavano Resource.Load di Unity e nelle nuove versioni con caricavano i diversi file .corto, abbiamo preferito usare appunto "Streaming Assets" e fare una piccola modifica: https://github.com/Vytek/UnityCortoSDKTest
8. In futuro stiamo studiando come create a runtime il materiale e la texture associata!
