# UnityCortoSDKTest
Unity Corto SDK Test Repo

Unity 2019.4.x Windows, Mac, Linux

Built from '2019.4/staging' branch; Version is '2019.4.28f1 (1381962e9d08) revision 1278358'; Using compiler version '191627012'
OS: 'Windows 10 Home; OS build 19044.1706; Version 2009; 64bit' Language: 'it' Physical Memory: 16259 MB

Unity Editor version:    2019.4.38f1 (fdbb7325fa47)
Branch:                  2019.4/staging
Build type:              Debug
Batch mode:              NO
macOS version:           Version 10.13.6 (Build 17G14042)
Darwin version:          17.7.0
Architecture:            x86_64
Running under Rosetta:   NO
Available memory:        8192 MB

ITA:

Primo prototipo di utilizzo dell'encoder/decoder Corto in Unity.

https://github.com/cnr-isti-vclab/corto

Per l'utilizzo abbiamo seguito questi passi:

1. Download ed installazione di CMake: https://cmake.org/download/
2. Configurazione per la generazione della solution (in questo caso Window per Visual Studio 2017 Community Edition)
3. Compilazione delle librerie libcorto, utility e decoder per Unity
4. Tramite KenShape abbiamo creato tre semplici mesh 3D poi compresse con l'utility corto

```
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
```

5. Creazione della cartella "Plugins" in cui inserire "cortocodec_unity.dll" (saranno necessari le altre versioni (linux, macosx, etc..) per renderlo cross-platform)
6. Creazione cartella "StreamingAssets" dove inserire i file .corto
7. Modifica degli script originali che usavano Resource.Load di Unity e nelle nuove versioni con caricavano i diversi file .corto, abbiamo preferito usare appunto "Streaming Assets" e fare una piccola modifica: https://github.com/Vytek/UnityCortoSDKTest/blob/762eaa168f3b1f568d8a12b0ff9c25094d4e2b4b/Assets/Scripts/CortoMeshLoader.cs#L14
8. In futuro stiamo studiando come create a runtime il materiale e la texture associata!

ENG:

First prototype to use the Corto encoder / decoder in Unity.

https://github.com/cnr-isti-vclab/corto

For use we followed these steps:

1. Download and install CMake: https://cmake.org/download/
2. Configuration for the generation of the solution (in this case Window for Visual Studio 2017 Community Edition)
3. Compilation of libcorto libraries, utilities and decoders for Unity
4. Using KenShape we created three simple 3D meshes which were then compressed with the short utility
5. Creation of the "Plugins" folder in which to insert "corticodec_unity.dll" (the other versions (linux, macosx, etc ..) will be needed to make it cross-platform)
6. Creation of the "StreamingAssets" folder where to insert the .corto files
7. Modification of the original scripts that used Resource.Load of Unity and in the new versions with loaded the different .corto files, we preferred to use "Streaming Assets" and make a small change: https://github.com/Vytek/UnityCortoSDKTest /blob/762eaa168f3b1f568d8a12b0ff9c25094d4e2b4b/Assets/Scripts/CortoMeshLoader.cs#L14
8. In the future we are studying how to create the material and the associated texture at runtime!

Collegamenti utili per lo sviluppo futuro:

- https://gist.github.com/supachailllpay/893cd5b0c31dff3bb025
- https://github.com/PhalanxHead/UnityRuntimeOBJLoaderDocs
- https://github.com/atteneder/KtxUnity
- https://github.com/prajwalshettydev/SnapObjLoader
- https://web.archive.org/web/20191229013646/http://wiki.unity3d.com/index.php/ObjImporter
- https://web.archive.org/web/20190728143516/http://wiki.unity3d.com/index.php/FastObjImporter

All models created by:

https://kenney.itch.io/kenney-shape
