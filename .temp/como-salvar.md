Para salvar a imagem do contêiner com todas as alterações que você fez e poder usá-la em outro computador, você precisa criar uma imagem Docker a partir do contêiner atualizado e, em seguida, salvá-la em um registro Docker (como o Docker Hub) ou como um arquivo de imagem.

Aqui estão os passos para realizar essa tarefa:

1. Certifique-se de que o contêiner esteja em execução. Se não estiver em execução, você pode iniciá-lo novamente usando o comando `docker-compose up -d`.

2. Use o comando `docker ps` para listar todos os contêineres em execução. Encontre o ID ou o nome do contêiner que deseja salvar como imagem.

3. Use o comando `docker commit` para criar uma nova imagem com base no estado atual do contêiner. Substitua `<container_id>` pelo ID ou nome do contêiner e `<image_name>` pelo nome desejado para a nova imagem. Por exemplo:

   ```bash
   docker commit <container_id> <image_name>
   ```

   Isso criará uma nova imagem Docker a partir do contêiner especificado.

4. Use o comando `docker images` para listar todas as imagens Docker disponíveis. Verifique se a imagem recém-criada está listada.

5. Opcionalmente, você pode adicionar uma tag à imagem usando o comando `docker tag`. Isso pode ajudar a identificar e organizar suas imagens. Por exemplo:

   ```bash
   docker tag <image_name> <repository_name>/<image_name>:<tag>
   ```

   Substitua `<repository_name>` pelo nome do repositório (por exemplo, seu nome de usuário no Docker Hub) e `<tag>` por uma tag personalizada.

6. Para salvar a imagem em um registro Docker (como o Docker Hub), você precisa fazer login no registro. Use o comando `docker login` e insira suas credenciais de conta.

7. Use o comando `docker push` para enviar a imagem para o registro Docker. Substitua `<repository_name>/<image_name>:<tag>` pelo nome da imagem completo, incluindo o repositório e a tag, se você adicionou uma. Por exemplo:

   ```bash
   docker push <repository_name>/<image_name>:<tag>
   ```

   Isso enviará a imagem para o registro Docker especificado.

8. Se você preferir salvar a imagem como um arquivo de imagem, use o comando `docker save`. Substitua `<image_name>` pelo nome da imagem que você deseja salvar e especifique o caminho para o arquivo de saída. Por exemplo:

   ```bash
   docker save -o <output_file.tar> <image_name>
   ```

   Isso criará um arquivo de imagem `.tar` contendo a imagem Docker.

Agora você tem a imagem salva, seja em um registro Docker ou como um arquivo de imagem. Em outro computador, você pode usar o comando `docker load` para carregar a imagem a partir do arquivo `.tar` ou `docker pull` para baixá-la do registro Docker, permitindo que você a utilize com todas as alterações feitas no contêiner original.
