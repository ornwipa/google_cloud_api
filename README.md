# Google Cloud Platform
The following instructions will build and deploy a container.
1. Write a sample application including `Program.cs` and `Startup.cs` as shown in this repository.
2. Write a Dockerfile in the same root directory as the application's source
3. To exclude files produced via local `dotnet` build operations from upload to Cloud Build, add a `.gcloudignore` file.
4. To log-in Google Cloud SDK, at terminal, run `gcloud auth login`
5. To create a new project, at terminal, run `gcloud projects create webapp-csharp-practice`
6. If necessary, set the billing information and link the project to the account on https://console.cloud.google.com
7. Run `gcloud config get-value project` to get the project name. If not correct then run `gcloud config set project webapp-csharp-practice` to set the current project
8. From the directory that contains the **Dockerfile**, run `gcloud builds submit --tag gcr.io/webapp-csharp-practice/helloworld` to build a container image using Cloud Build
9. Run `gcloud run deploy --image gcr.io/webapp-csharp-practice/helloworld --platform managed` to Deploy the applition to Cloud Run
Done. Service URL: https://helloworld-ozgs724boq-uc.a.run.app
