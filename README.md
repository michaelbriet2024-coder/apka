# HackLab Academy — Android (v1.0)

Aplicativo educativo em português, criado para aprender programação, Linux, redes, hacking ético e perícia digital. Interface dark e responsiva, exercícios, terminal fictício e vibração tátil.

## Arquivos

- `app/src/main/assets/index.html` — interface e lógica offline (pode ser aberta no navegador do computador para demonstração).
- `app/src/main/java/com/brietlabs/hacklab/MainActivity.java` — aplicativo Android nativo que carrega a interface local e fornece vibração através do Android.
- Arquivos Gradle — projeto importável no Android Studio.

## Gerar o APK automaticamente pelo GitHub (sem Android Studio)

O projeto inclui `.github/workflows/gerar-apk.yml` para compilar no **GitHub Actions**, gratuitamente dentro dos limites da plataforma. **Ainda não foi compilado nem testado em aparelho Android neste ambiente.**

1. Crie um repositório no GitHub e envie **todo o conteúdo desta pasta**, inclusive a pasta oculta `.github` (não envie apenas o ZIP sem extrair).
2. Na aba **Actions**, selecione **Gerar APK Android**, clique em **Run workflow** (ou faça um commit na branch `main` ou `master`).
3. Depois que a execução terminar com sucesso, abra a execução e procure o artefato **HackLab_Academy_APK** na seção *Artifacts*.
4. Baixe o ZIP do artefato, extraia `HackLab_Academy.apk`, transfira para seu celular e instale autorizando **Instalar apps desconhecidos** somente para este arquivo de sua confiança.
5. O APK resultante será uma versão **debug**, assinada para testes. Para distribuir na Play Store é necessário preparar uma versão release assinada com sua própria chave.

> O GitHub Actions exige uma conta no GitHub e acesso ao repositório. O código deve ficar na raiz do repositório.

## Como gerar o APK pelo Android Studio

1. Instale o Android Studio em um computador Windows, macOS ou Linux.
2. Abra a pasta `HackLabAcademy` com **File → Open**.
3. Aguarde o Android Studio instalar/sincronizar as dependências Gradle e o SDK Android 35 (internet necessária nessa etapa).
4. Use **Gradle 8.9**. Este pacote não inclui o `gradle-wrapper.jar`; se o Android Studio não reconhecer uma instalação do Gradle, configure uma distribuição local do Gradle 8.9 ou gere um wrapper no terminal com `gradle wrapper --gradle-version 8.9`. Para compilação automatizada, prefira o GitHub Actions acima.
5. No menu **Build → Build App Bundle(s) / APK(s) → Build APK(s)**, gere o pacote.
6. Encontre o arquivo em `app/build/outputs/apk/debug/app-debug.apk` e instale no seu celular Android.

## Funcionalidades

- 6 trilhas de ensino e 16 aulas com perguntas e explicações.
- 5 missões simuladas em terminal educativo, sem comandos reais.
- Experiência (XP), níveis, medalhas e progresso persistido localmente.
- Vibração curta em botões, configurável em Ajustes.
- Executa offline; não precisa de login, servidor, banco de dados remoto nem permissões de internet.

## Notas de segurança e limites

O terminal não executa comandos no Android. Só reconhece respostas fixas de um ambiente fictício, para ensino seguro.
O progresso fica no armazenamento local do WebView. Desinstalar ou limpar dados do aplicativo pode apagá-lo.
O arquivo HTML aberto diretamente em um navegador pode não ter vibração (suporte do navegador/dispositivo).
O projeto acompanha código-fonte, **não um APK previamente compilado**. A compilação ainda precisa ser realizada no Android Studio.

## Atribuição

HackLab Academy · BrietLabs.
