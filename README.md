# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontends goes here
`db/` | your domain models and data go here
`srv/` | your service models and code go here
`package.json` | project metadata and configuration
`readme.md` | this getting started guide


## Next Steps

- Open a new terminal and run `cds watch` 
- (in VS Code simply choose _**Terminal** > Run Task > cds watch_)
- Start adding content, for example, a [db/schema.cds](db/schema.cds).


## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.

## Bash Terminal Output

user: projects $ cds init shop-manager
Creating new cap project in ./shop-manager

Adding feature 'nodejs'... 
Done adding features

Continue with 'cd shop-manager'
Find samples on https://github.com/SAP-samples/cloud-cap-samples
Learn about next steps at https://cap.cloud.sap

user: projects $ cd shop-manager/
user: shop-manager $ cds add mta
Adding feature(s) to project in current folder

Adding feature 'mta'... 
Done adding features


user: shop-manager $ cds add samples
Adding feature(s) to project in current folder

Adding feature 'samples'... 
Done adding features

user: shop-manager $ npm install

added 1 package, and audited 176 packages in 581ms

12 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
user: shop-manager $ mbt build
[2023-03-30 17:26:10]  INFO Cloud MTA Build Tool version 1.2.18
[2023-03-30 17:26:10]  INFO generating the "Makefile_20230330172610.mta" file...
[2023-03-30 17:26:10]  INFO done
[2023-03-30 17:26:10]  INFO executing the "make -f Makefile_20230330172610.mta p=cf mtar= strict=true mode=" command...
[2023-03-30 17:26:10]  INFO validating the MTA project
[2023-03-30 17:26:10]  INFO running the "before-all" build...
[2023-03-30 17:26:10]  INFO executing the "npx -p @sap/cds-dk cds build --production" command...
.[cds] - the following build tasks will be executed
[cds] -    {
     "build": {
       "target": "gen",
       "tasks": [
         {"for":"hana", "src":"db", "options":{"model":["db","srv","app"]}},
         {"for":"nodejs", "src":"srv", "options":{"model":["db","srv","app"]}}
       ]
     }
   }

[cds] - building project [/home/user/projects/shop-manager], clean [true]
[cds] - cds [6.7.0], compiler [3.8.2], home [/home/user/projects/shop-manager/node_modules/@sap/cds]

[cds] - done > wrote output to:
   gen/db/package.json
   gen/db/src/.hdiconfig
   gen/db/src/gen/.hdiconfig
   gen/db/src/gen/.hdinamespace
   gen/db/src/gen/CatalogService.Books.hdbview
   gen/db/src/gen/data/my.bookshop-Books.csv
   gen/db/src/gen/data/my.bookshop-Books.hdbtabledata
   gen/db/src/gen/my.bookshop.Books.hdbtable
   gen/db/undeploy.json
   gen/srv/.cdsrc.json
   gen/srv/package-lock.json
   gen/srv/package.json
   gen/srv/srv/csn.json

[cds] - build completed in 348 ms

[2023-03-30 17:26:12]  INFO validating the MTA project
[2023-03-30 17:26:12]  INFO building the "shop-manager-srv" module...
[2023-03-30 17:26:12]  INFO executing the "npm clean-install --production" command...
npm WARN config production Use `--omit=dev` instead.
.
added 67 packages, and audited 68 packages in 1s

8 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
[2023-03-30 17:26:13]  INFO the build results of the "shop-manager-srv" module will be packaged and saved in the "/home/user/projects/shop-manager/.shop-manager_mta_build_tmp/shop-manager-srv" folder
[2023-03-30 17:26:14]  INFO finished building the "shop-manager-srv" module
[2023-03-30 17:26:14]  INFO building the "shop-manager-db-deployer" module...
[2023-03-30 17:26:14]  INFO executing the "npm install --production" command...
npm WARN config production Use `--omit=dev` instead.
....
added 31 packages, and audited 32 packages in 4s

found 0 vulnerabilities
[2023-03-30 17:26:18]  INFO the build results of the "shop-manager-db-deployer" module will be packaged and saved in the "/home/user/projects/shop-manager/.shop-manager_mta_build_tmp/shop-manager-db-deployer" folder
[2023-03-30 17:26:24]  INFO finished building the "shop-manager-db-deployer" module
[2023-03-30 17:26:24]  INFO running the "after-all" build...
[2023-03-30 17:26:24]  INFO generating the metadata...
[2023-03-30 17:26:24]  INFO generating the "/home/user/projects/shop-manager/.shop-manager_mta_build_tmp/META-INF/mtad.yaml" file...
[2023-03-30 17:26:24]  INFO generating the MTA archive...
[2023-03-30 17:26:27]  INFO the MTA archive generated at: /home/user/projects/shop-manager/mta_archives/shop-manager_1.0.0.mtar
[2023-03-30 17:26:27]  INFO cleaning temporary files...
user: shop-manager $ git init
Initialized empty Git repository in /home/user/projects/shop-manager/.git/
user: shop-manager $ git add -A
user: shop-manager $ git remote add origin https://github.com/SheshnathA/cap-deployment-onCF-HANADB-MTA.git
user: shop-manager $ git config pull.rebase true
user: shop-manager $ git pull origin main  --allow-unrelated-histories
fatal: Updating an unborn branch with changes added to the index.
user: shop-manager $ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .cdsrc.json
        new file:   .gitignore
        new file:   .vscode/extensions.json
        new file:   .vscode/launch.json
        new file:   .vscode/tasks.json
        new file:   README.md
        new file:   db/data-model.cds
        new file:   db/data/my.bookshop-Books.csv
        new file:   db/src/.hdiconfig
        new file:   db/undeploy.json
        new file:   mta.yaml
        new file:   package-lock.json
        new file:   package.json
        new file:   srv/cat-service.cds

user: shop-manager $ git commit -m "cap sample project for deployment on Cf using MTA with Hana DB"
[main (root-commit) 7b9d722] cap sample project for deployment on Cf using MTA with Hana DB
 14 files changed, 3831 insertions(+)
 create mode 100644 .cdsrc.json
 create mode 100644 .gitignore
 create mode 100644 .vscode/extensions.json
 create mode 100644 .vscode/launch.json
 create mode 100644 .vscode/tasks.json
 create mode 100644 README.md
 create mode 100644 db/data-model.cds
 create mode 100644 db/data/my.bookshop-Books.csv
 create mode 100644 db/src/.hdiconfig
 create mode 100644 db/undeploy.json
 create mode 100644 mta.yaml
 create mode 100644 package-lock.json
 create mode 100644 package.json
 create mode 100644 srv/cat-service.cds
user: shop-manager $ git push origin HEAD:main
Enumerating objects: 21, done.
Counting objects: 100% (21/21), done.
Delta compression using up to 8 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (21/21), 39.06 KiB | 5.58 MiB/s, done.
Total 21 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/SheshnathA/cap-deployment-onCF-HANADB-MTA.git
 * [new branch]      HEAD -> main
user: shop-manager $ 
