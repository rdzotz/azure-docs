---
author: eric-urban
ms.service: cognitive-services
ms.topic: include
ms.date: 09/18/2022
ms.author: eur
ms.devlang: csharp
---

[!INCLUDE [Header](header.md)]

[!INCLUDE [Introduction](intro.md)]

## Prerequisites

[!INCLUDE [Prerequisites](azure-prerequisites.md)]

## Run post-call transcription analysis with C#

Follow these steps to run post-call transcription analysis from an audio file.

1. Copy the <a href="https://github.com/Azure-Samples/cognitive-services-speech-sdk/tree/master/scenarios/csharp/dotnetcore/call-center/"  title="Copy the samples"  target="_blank">scenarios/csharp/dotnetcore/call-center/</a> sample files from GitHub. If you have [Git installed](https://git-scm.com/downloads), open a command prompt and run the `git clone` command to download the Speech SDK samples repository.
    ```dotnetcli
    git clone https://github.com/Azure-Samples/cognitive-services-speech-sdk.git
    ```
1. Open a command prompt and change to the project directory.
    ```dotnetcli
    cd <your-local-path>/scenarios/csharp/dotnetcore/call-center/call-center/
    ```
1. Build the project with the .NET CLI.
    ```dotnetcli
    dotnet build
    ```
1. Run the application with your preferred command line arguments. See [usage and arguments](#usage-and-arguments) for the available options. 
    
    Here's an example that transcribes from an example audio file at [GitHub](https://github.com/Azure-Samples/cognitive-services-speech-sdk/raw/master/scenarios/call-center/sampledata/Call1_separated_16k_health_insurance.wav):
    ```dotnetcli
    dotnet run --languageKey YourResourceKey --languageEndpoint YourResourceEndpoint --speechKey YourResourceKey --speechRegion YourResourceRegion --input "https://github.com/Azure-Samples/cognitive-services-speech-sdk/raw/master/scenarios/call-center/sampledata/Call1_separated_16k_health_insurance.wav" --stereo  --output summary.json
    ```
    
    If you already have a transcription for input, here's an example that only requires a Language resource:
    ```dotnetcli
    dotnet run --languageKey YourResourceKey --languageEndpoint YourResourceEndpoint --jsonInput "YourTranscriptionFile.json" --stereo  --output summary.json
    ```
    
    Replace `YourResourceKey` with your Cognitive Services resource key, replace `YourResourceRegion` with your Cognitive Services resource [region](~/articles/cognitive-services/speech-service/regions.md) (such as `eastus`), and replace `YourResourceEndpoint` with your Cognitive Services endpoint. Make sure that the paths specified by `--input` and `--output` are valid. Otherwise you must change the paths.
    > [!IMPORTANT]
    > Remember to remove the key from your code when you're done, and never post it publicly. For production, use a secure way of storing and accessing your credentials like [Azure Key Vault](../../../../../key-vault/general/overview.md). See the Cognitive Services [security](../../../../cognitive-services-security.md) article for more information.


## Check results

[!INCLUDE [Example output](example-output.md)]

## Usage and arguments

Usage: `call-center -- [...]`

[!INCLUDE [Usage arguments](usage-arguments.md)]


## Clean up resources

[!INCLUDE [Delete resource](delete-resource.md)]





