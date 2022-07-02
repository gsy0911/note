CodeBuild
#########


`“Too Many Requests.” でビルドが失敗する…。AWS CodeBuild で IP ガチャを回避するために Docker Hub ログインしよう！という話 <https://dev.classmethod.jp/articles/codebuild-has-to-use-dockerhub-login-to-avoid-ip-gacha/>`_

SecretsManagerに値を登録する

.. code-block:: yaml

    env:
      secrets-manager:
        DOCKERHUB_USER: arn:aws:secretsmanager:ap-northeast-1:123456789012:secret:docker-hub-eRuNNr:username
        DOCKERHUB_PASS: arn:aws:secretsmanager:ap-northeast-1:123456789012:secret:docker-hub-eRuNNr:password


    phases:
      pre_build:
        commands:
          # ECR へのログイン
          - echo Logging in to Amazon ECR...
          - $(aws ecr get-login --no-include-email --region $AWS_DEFAULT_REGION)
          # Docker Hub へのログイン
          - echo Logging in to Docker Hub...
          - echo $DOCKERHUB_PASS | docker login -u $DOCKERHUB_USER --password-stdin