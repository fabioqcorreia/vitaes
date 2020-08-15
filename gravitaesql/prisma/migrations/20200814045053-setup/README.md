# Migration `20200814045053-setup`

This migration has been generated by Ramon Saboya at 8/14/2020, 4:50:53 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE `vitaes`.`User` (
`autosave` boolean NOT NULL DEFAULT false ,`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`firebaseId` varchar(191) NOT NULL  ,`recordsOrder` varchar(191) NOT NULL  ,`sectionOrder` varchar(191) NOT NULL  ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`CV` (
`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`ownerVid` varchar(191) NOT NULL ,`recordsOrder` varchar(191) NOT NULL  ,`sectionOrder` varchar(191) NOT NULL  ,`title` varchar(191)   ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`Record` (
`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`hidden` boolean NOT NULL DEFAULT false ,`ownerVid` varchar(191) NOT NULL ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordAcademic` (
`articleLink` varchar(191)   ,`description` varchar(191)   ,`endDate` datetime(3)   ,`institutionVid` varchar(191)  ,`locationVid` varchar(191)  ,`recordVid` varchar(191) NOT NULL ,`startDate` datetime(3) NOT NULL  ,`title` varchar(191) NOT NULL  ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordAchievement` (
`certificateLink` varchar(191)   ,`description` varchar(191)   ,`endDate` datetime(3)   ,`institutionVid` varchar(191)  ,`locationVid` varchar(191)  ,`position` varchar(191)   ,`recordVid` varchar(191) NOT NULL ,`startDate` datetime(3) NOT NULL  ,`title` varchar(191) NOT NULL  ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordEducation` (
`course` varchar(191) NOT NULL  ,`description` varchar(191)   ,`endDate` datetime(3)   ,`institutionVid` varchar(191)  ,`locationVid` varchar(191)  ,`recordVid` varchar(191) NOT NULL ,`startDate` datetime(3) NOT NULL  ,`teacher` varchar(191)   ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordLanguage` (
`level` varchar(191) NOT NULL  ,`name` varchar(191) NOT NULL  ,`recordVid` varchar(191) NOT NULL ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordPersonal` (
`address` varchar(191)   ,`birthday` datetime(3)   ,`email` varchar(191)   ,`github` varchar(191)   ,`homepage` varchar(191)   ,`linkedin` varchar(191)   ,`name` varchar(191)   ,`phone` varchar(191)   ,`recordVid` varchar(191) NOT NULL ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordProject` (
`description` varchar(191)   ,`endDate` datetime(3)   ,`locationVid` varchar(191)  ,`programmingLanguage` varchar(191)   ,`recordVid` varchar(191) NOT NULL ,`repositoryLink` varchar(191)   ,`startDate` datetime(3) NOT NULL  ,`title` varchar(191) NOT NULL  ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordSkill` (
`level` varchar(191)   ,`name` varchar(191) NOT NULL  ,`recordVid` varchar(191) NOT NULL ,`type` varchar(191) NOT NULL  ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`RecordWork` (
`description` varchar(191)   ,`endDate` datetime(3)   ,`institutionVid` varchar(191)  ,`locationVid` varchar(191)  ,`recordVid` varchar(191) NOT NULL ,`role` varchar(191) NOT NULL  ,`startDate` datetime(3) NOT NULL  ,
    PRIMARY KEY (`recordVid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`Institution` (
`abbreviaton` varchar(191)   ,`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`name` varchar(191) NOT NULL  ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`Location` (
`cityTown` varchar(191)   ,`country` varchar(191)   ,`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`governingDistrict` varchar(191)   ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`BugReport` (
`authorVid` varchar(191)  ,`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`data` varchar(191)   ,`description` varchar(191)   ,`email` varchar(191)   ,`title` varchar(191) NOT NULL  ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`Alert` (
`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`message` varchar(191) NOT NULL  ,`type` ENUM('INFO', 'WARNING', 'ERROR') NOT NULL  ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`Gatekeeper` (
`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`description` varchar(191)   ,`name` varchar(191) NOT NULL  ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`Template` (
`baseFolder` varchar(191) NOT NULL  ,`command` varchar(191) NOT NULL  ,`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`name` varchar(191) NOT NULL  ,`updatedAt` datetime(3) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`TemplateParam` (
`createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ,`defaultValue` varchar(191) NOT NULL  ,`displayName` varchar(191) NOT NULL  ,`name` varchar(191) NOT NULL  ,`templateVid` varchar(191) NOT NULL ,`updatedAt` datetime(3) NOT NULL  ,`values` varchar(191) NOT NULL  ,`vid` varchar(191) NOT NULL  ,
    PRIMARY KEY (`vid`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`_GatekeeperToUser` (
`A` varchar(191) NOT NULL ,`B` varchar(191) NOT NULL 
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE TABLE `vitaes`.`_CVToRecord` (
`A` varchar(191) NOT NULL ,`B` varchar(191) NOT NULL 
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE UNIQUE INDEX `User.firebaseId` ON `vitaes`.`User`(`firebaseId`)

CREATE UNIQUE INDEX `Gatekeeper.name` ON `vitaes`.`Gatekeeper`(`name`)

CREATE UNIQUE INDEX `Template.name` ON `vitaes`.`Template`(`name`)

CREATE UNIQUE INDEX `_GatekeeperToUser_AB_unique` ON `vitaes`.`_GatekeeperToUser`(`A`,`B`)

CREATE  INDEX `_GatekeeperToUser_B_index` ON `vitaes`.`_GatekeeperToUser`(`B`)

CREATE UNIQUE INDEX `_CVToRecord_AB_unique` ON `vitaes`.`_CVToRecord`(`A`,`B`)

CREATE  INDEX `_CVToRecord_B_index` ON `vitaes`.`_CVToRecord`(`B`)

ALTER TABLE `vitaes`.`CV` ADD FOREIGN KEY (`ownerVid`) REFERENCES `vitaes`.`User`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`Record` ADD FOREIGN KEY (`ownerVid`) REFERENCES `vitaes`.`User`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordAcademic` ADD FOREIGN KEY (`locationVid`) REFERENCES `vitaes`.`Location`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordAcademic` ADD FOREIGN KEY (`institutionVid`) REFERENCES `vitaes`.`Institution`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordAcademic` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordAchievement` ADD FOREIGN KEY (`locationVid`) REFERENCES `vitaes`.`Location`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordAchievement` ADD FOREIGN KEY (`institutionVid`) REFERENCES `vitaes`.`Institution`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordAchievement` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordEducation` ADD FOREIGN KEY (`locationVid`) REFERENCES `vitaes`.`Location`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordEducation` ADD FOREIGN KEY (`institutionVid`) REFERENCES `vitaes`.`Institution`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordEducation` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordLanguage` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordPersonal` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordProject` ADD FOREIGN KEY (`locationVid`) REFERENCES `vitaes`.`Location`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordProject` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordSkill` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordWork` ADD FOREIGN KEY (`locationVid`) REFERENCES `vitaes`.`Location`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordWork` ADD FOREIGN KEY (`institutionVid`) REFERENCES `vitaes`.`Institution`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`RecordWork` ADD FOREIGN KEY (`recordVid`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`BugReport` ADD FOREIGN KEY (`authorVid`) REFERENCES `vitaes`.`User`(`vid`) ON DELETE SET NULL ON UPDATE CASCADE

ALTER TABLE `vitaes`.`TemplateParam` ADD FOREIGN KEY (`templateVid`) REFERENCES `vitaes`.`Template`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`_GatekeeperToUser` ADD FOREIGN KEY (`A`) REFERENCES `vitaes`.`Gatekeeper`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`_GatekeeperToUser` ADD FOREIGN KEY (`B`) REFERENCES `vitaes`.`User`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`_CVToRecord` ADD FOREIGN KEY (`A`) REFERENCES `vitaes`.`CV`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE

ALTER TABLE `vitaes`.`_CVToRecord` ADD FOREIGN KEY (`B`) REFERENCES `vitaes`.`Record`(`vid`) ON DELETE CASCADE ON UPDATE CASCADE
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200814045053-setup
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,237 @@
+datasource db {
+  provider  = "mysql"
+  url = "***"
+}
+
+generator prisma_client {
+  provider  = "prisma-client-js"
+}
+
+model User {
+  vid           String        @id
+  firebaseId    String        @unique
+  autosave      Boolean       @default(false)
+  sectionOrder  String
+  recordsOrder  String
+  createdAt     DateTime      @default(now())
+  updatedAt     DateTime      @updatedAt
+
+  records       Record[]
+  cvs           CV[]
+  gatekeepers   Gatekeeper[]
+  bugReports    BugReport[]
+}
+
+model CV {
+  vid           String    @id
+  title         String?
+  sectionOrder  String
+  recordsOrder  String
+  createdAt     DateTime  @default(now())
+  updatedAt     DateTime  @updatedAt
+
+  records       Record[]
+
+  owner         User      @relation(fields: [ownerVid], references: [vid])
+  ownerVid      String
+}
+
+model Record {
+  vid       String    @id
+  hidden    Boolean   @default(false)
+  createdAt DateTime  @default(now())
+  updatedAt DateTime  @updatedAt
+
+  cvs       CV[]
+
+  owner     User      @relation(fields: [ownerVid], references: [vid])
+  ownerVid  String
+}
+
+model RecordAcademic {
+  title           String
+  startDate       DateTime
+  endDate         DateTime?
+  description     String?
+  articleLink     String?
+
+  location        Location?     @relation(fields: [locationVid], references: [vid])
+  locationVid     String?
+  institution     Institution?  @relation(fields: [institutionVid], references: [vid])
+  institutionVid  String?
+
+  record          Record        @relation(fields: [recordVid], references: [vid])
+  recordVid       String        @id
+}
+
+model RecordAchievement {
+  title           String
+  startDate       DateTime
+  endDate         DateTime?
+  description     String?
+  position        String?
+  certificateLink String?
+
+  location        Location?     @relation(fields: [locationVid], references: [vid])
+  locationVid     String?
+  institution     Institution?  @relation(fields: [institutionVid], references: [vid])
+  institutionVid  String?
+
+  record          Record        @relation(fields: [recordVid], references: [vid])
+  recordVid       String        @id
+}
+
+model RecordEducation {
+  course          String
+  startDate       DateTime
+  endDate         DateTime?
+  description     String?
+  teacher         String?
+
+  location        Location?     @relation(fields: [locationVid], references: [vid])
+  locationVid     String?
+  institution     Institution?  @relation(fields: [institutionVid], references: [vid])
+  institutionVid  String?
+
+  record          Record        @relation(fields: [recordVid], references: [vid])
+  recordVid       String        @id
+}
+
+model RecordLanguage {
+  name      String
+  level     String
+
+  record    Record  @relation(fields: [recordVid], references: [vid])
+  recordVid String  @id
+}
+
+model RecordPersonal {
+  name      String?
+  email     String?
+  homepage  String?
+  phone     String?
+  address   String?
+  linkedin  String?
+  github    String?
+  birthday  DateTime?
+
+  record    Record    @relation(fields: [recordVid], references: [vid])
+  recordVid String    @id
+}
+
+model RecordProject {
+  title               String
+  startDate           DateTime
+  endDate             DateTime?
+  description         String?
+  programmingLanguage String?
+  repositoryLink      String?
+
+  location            Location? @relation(fields: [locationVid], references: [vid])
+  locationVid         String?
+
+  record              Record    @relation(fields: [recordVid], references: [vid])
+  recordVid           String    @id
+}
+
+model RecordSkill {
+  name      String
+  type      String
+  level     String?
+
+  record    Record  @relation(fields: [recordVid], references: [vid])
+  recordVid String  @id
+}
+
+model RecordWork {
+  role            String
+  startDate       DateTime
+  endDate         DateTime?
+  description     String?
+
+  location        Location?     @relation(fields: [locationVid], references: [vid])
+  locationVid     String?
+  institution     Institution?  @relation(fields: [institutionVid], references: [vid])
+  institutionVid  String?
+
+  record          Record        @relation(fields: [recordVid], references: [vid])
+  recordVid       String        @id
+}
+
+model Institution {
+  vid         String    @id
+  name        String
+  abbreviaton String?
+  createdAt   DateTime  @default(now())
+  updatedAt   DateTime  @updatedAt
+}
+
+model Location {
+  vid               String    @id
+  country           String?
+  governingDistrict String?
+  cityTown          String?
+  createdAt         DateTime  @default(now())
+  updatedAt         DateTime  @updatedAt
+}
+
+model BugReport {
+  vid         String    @id
+  title       String
+  email       String?
+  description String?
+  data        String?
+  createdAt   DateTime  @default(now())
+  updatedAt   DateTime  @updatedAt
+
+  author      User?     @relation(fields: [authorVid], references: [vid])
+  authorVid   String?
+}
+
+enum AlertType {
+  INFO
+  WARNING
+  ERROR
+}
+
+model Alert {
+  vid       String    @id
+  message   String
+  type      AlertType
+  createdAt DateTime  @default(now())
+  updatedAt DateTime  @updatedAt
+}
+
+model Gatekeeper {
+  vid           String    @id
+  name          String    @unique
+  description   String?
+  createdAt     DateTime  @default(now())
+  updatedAt     DateTime  @updatedAt
+  
+  allowedUsers  User[]
+}
+
+model Template {
+  vid         String          @id
+  name        String          @unique
+  baseFolder  String
+  command     String
+  createdAt   DateTime        @default(now())
+  updatedAt   DateTime        @updatedAt
+
+  params      TemplateParam[]
+}
+
+model TemplateParam {
+  vid           String    @id
+  name          String
+  displayName   String
+  defaultValue  String
+  values        String
+  createdAt     DateTime  @default(now())
+  updatedAt     DateTime  @updatedAt
+
+  template      Template  @relation(fields: [templateVid], references: [vid])
+  templateVid   String
+}
```

