<div align = "center">
<h1>Projeto JavaFX com JDBC</h1>
<h3>Programação Orientada a Objetos com Java</h3>
<hr>

![Java](https://img.shields.io/badge/-Java-DE252C?style=flat-square&logo=java&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f?style=flat-square&logo=mysql&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-square&logo=windows&logoColor=white)

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/Flgc/javafx-jdbc/blob/main/LICENSE)
<br>
<br>

</div>

<div align="center">

[**Sobre**](https://github.com/Flgc/javafx-jdbc#-sobre-o-projeto) &nbsp;&nbsp;**|**&nbsp;&nbsp;
[**Demonstração**](https://github.com/Flgc/javafx-jdbc#-demonstra%C3%A7%C3%A3o-web) &nbsp;&nbsp;**|**&nbsp;&nbsp;
[**Como instalar e executar o projeto**](https://github.com/Flgc/javafx-jdbc#-como-instalar-e-executar-o-projeto) &nbsp;&nbsp;**|**&nbsp;&nbsp;
[**Contato**](https://github.com/Flgc/javafx-jdbc#-contato) &nbsp;&nbsp;**|**&nbsp;&nbsp;

</div><br><br>

## 📃 Sobre o projeto

https://github.com/Flgc/javafx-jdbc

<p align="justify">O projeto foi desenvolvido durante o curso de Java COMPLETO - Programação Orientada a Objetos + Projetos.</p>

<p align="justify">Objetivo geral: Desenvolvimento de aplicações JavaFX com JDBC e o aprofundamento dos fundamentos e a utilização das ferramentas. O principal requisito para esse projeto é que o estudante já tenha conhecimento em OO, Lambda, JDBC e JavaFx com SceneBuilder.
<br><br>

## ✨ Features

<b>✔ Local project

- Checklist:</b>

  User libraries: JavaFX, MySQLConnector
  Run configurarions -> VM arguments: --module-path [path]\java-libs\javafx-sdk\lib --add-modules=javafx.fxml,javafx.controls<br><br>

<b>✔ Main view

- Checklist:</b>
  Create FXML "MainView" (package "gui")
  Load FXML in Main
  Update Main.java<br><br>

<b>✔ Main view design

- Checklist:</b>
  Design MainView.fxml
  Customize menu items
  Update Main.java<br><br>

<b>✔ Main view controller

- Checklist:</b>
  Create controller
  In view, associate controller, ids, events<br><br>

<b>✔ About view

- Checklist:</b>
  Include util classes to the project (Alerts.java, Constraints.java)
  Create About.fxml (VBox)
  In Main.java, expose mainScene reference
  In MainViewController.java, create loadView method<br><br>

<b>✔ DepartmentList view design

- Checklist:</b>
  Create DepartmentList.fxml (VBox)
  In MainViewController.java, load DepartmentList<br><br>

<b>✔ DepartmentList controller

- Checklist:</b>
  Create model.entities.Department.java
  Create DepartmentListController.java
  In view, associate controller, ids, events<br><br>

<b>✔ DepartmentService

- Checklist:</b>
  Create model.services.DepartmentService.java with findAll method
  In DepartmentListController:
  Create DepartmentService dependency with set method
  Create ObservableList<Department>
  Create updateTableViewData method<br><br>

<b>✔ Initializing action as parameter

- Checklist:</b>
  Add a Consumer<T> parameter to loadView method
  After loading view, call accept from the Consumer
  Add a consumer instance on loadView calls<br><br>

<b>✔ Adding database access

- Prerequisites:</b>
  MySQL server installed and running
  Database created and instantiated
  Data access layer implemented (DAO pattern)<br><br>

- <b>Checklist:</b>
  Add model.entities.Seller.java
  Add db.properties do project
  Add data access packages to project:

  - db
  - model.dao
  - model.dao.impl

  In DepartmentService, add DepartmentDao dependency with Factory call<br><br>

<b>✔ DepartmentForm (dialog) design

- Checklist:</b>
  Create gui.util.Utils.java with currentStage method
  Create DepartmentForm.fxml (AnchorPane)

  - GridPane 3x3 (anchors: 20 top, 20 left)
  - Id text box: not editable
  - Label error: red
  - HBox (spacing: 5)

  In DepartmentListController, create createDialogForm method
  Call createDialogForm on "new" button action
  <br>

<b>✔ DepartmentFormController

- Checklist:</b>
  Create DepartmentFormController.java
  In view, associate controller, ids, events<br><br>

<b>✔ Passing a Department object to DepartmentForm view

- Checklist:</b>
  In DepartmentFormController

  - Create a Department dependency with set method
  - Create updateFormData method

  In DepartmentListController

  - Update onBtNewAction method
  - Update createDialogForm method<br><br>

<b>✔ Saving a new Department

- Checklist:</b>
  In Utils, implement tryParseToInt method
  In DepartmentService, create saveOrUpdate method
  In DepartmentFormController

  - Create a DepartmentService dependency with set method
  - Implement onBtSaveAction
  - Implement onBtCancelAction

  In DepartmentListController, inject DepartmentService instance<br><br>

<b>✔ Observer design pattern to update tableview

- Checklist:</b>
  Create interface gui.listeners.DataChangeListener
  In DepartmentFormController (subject)

  - Create List<DataChangeListener> dependency with subscribe method
  - Notify subscribers when needed

  In DepartmentListController (observer)

  - Implement DataChangeListener interface
  - Subscribe for DepartmentFormController<br><br>

<b>✔ Validation exception

- Checklist:</b>
  Create model.exceptions.ValidationException
  In DepartmentFormController

  - In getFormData method, implement verifications and throw ValidationException
  - Implement setErrorMessages method
  - In onBtSaveAction, catch ValidationException<br><br>

<b>✔ Update department

- References:</b>
  https://stackoverflow.com/questions/32282230/fxml-javafx-8-tableview-make-a-delete-button-in-each-row-anddelete-the-row-a<br>
  <b>
- Checklist:</b>
  In DepartmentListController

  - Create new attribute: TableColumn<Department, Department> tableColumnEDIT;
  - Create initEditButtons method
  - In updateTableViewData, call initEditButtons

  In DepartmentList.fxml

  - Include new table column
  - Associate id <br><br>

<b>✔ Remove department

- Checklist:</b>
  In Alerts, create showConfirmation method
  In DepartmentService, create remove method
  In DepartmentListController

  - Create new attribute: TableColumn<Department, Department> tableColumnREMOVE;
  - Create initRemoveButtons method

    - Catch DbIntegrityException

  - In updateTableViewData, call initRemoveButtons

  In DepartmentList.fxml

  - Include new table column
  - Associate id<br><br>

<b>✔ Deleting .settings folder

- Checklist:</b>
  .gitignore: .settings/
  Delete .settings/ folder<br><br>

<b>✔ Saving Seller

- Checklist:</b>
  Clone SellerService

  - Replace: Department -> Seller

  Clone SellerListController

  - Replace: Department -> Seller
  - Comment createDialogForm

  Clone SellerList.fxml

  - Replace: Department -> Seller

  Update MainViewController.onMenuItemSellerAction<br><br>

<b>✔ Seller TableView

- References:</b>
  https://stackoverflow.com/questions/47484280/format-of-date-in-the-javafx-tableview<br>
  <b>
- Checklist:</b>
  gui.utils.Util.java

  - formatTableColumnDate method
  - formatTableColumnDouble method

  SellerListController

  - TableColumn attributes (Email, BirthDate, BaseSalary)
  - Update initializeNodes

  SellerListView

  - TableColumn (Email, BirthDate, BaseSalary)
  - Associate fx:id <br><br>

<b>✔ SellerForm

- Checklist:</b>

  Clone SellerFormController

  - Replace: Department -> Seller

  Clone SellerForm view

  - Replace: Department -> Seller

  SellerListController

  - Uncomment createDialogForm<br><br>

<b>✔ TextField & DatePicker

- References:</b>
  https://stackoverflow.com/questions/26831978/javafx-datepicker-getvalue-in-a-specific-format<br>
  <b>

- Checklist:</b>
  gui.utils.Util.java

  - formatDatePicker method

  TextField & DatePicker attributes (Email, BirthDate, BaseSalary)
  Label error attributes (Email, BirthDate, BaseSalary)
  Edit SellerFormView
  Bugfix: SellerDaoJDBC.instantiateSeller

      obj.setBirthDate(new java.util.Date(rs.getTimestamp("BirthDate"). getTime()));

  Update: initializeNodes
  Update: updateFormData<br><br>

<b>✔ Department ComboBox

- Checklist:</b>

  Update controller:

  - DepartmentService dependency

    - attribute
    - set method

  - ComboBox<Department> comboBoxDepartment
  - ObservableList<Department> obsList

    - loadAssociatedObjects

  - initializeComboBoxDepartment
  - updateFormData

  Update view:

  - ComboBox
  - fx:id

<b>✔ Saving Seller

- Checklist:</b>
  Update: getFormData
  Update: setErrorMessages<br><br>

## 🌎 Demonstração Web

<h1>
<img src="public/javafx_jdbc.gif">
</h1>

# 🚀 Tecnologias utilizadas

- Java
- JavaFX
- MySQL
- SeneBuilder
- JDBC
- Eclipse 4.9 2018-09

# 🔧 Como instalar e executar o projeto

Pré-requisitos: npm / yarn

```bash
# clonar repositório
git clone https://github.com/Flgc/javafx-jdbc


# instalar dependências
Java 11
Javafx
mysql-connector-java-8.0.26
Instalar o plug-in E(fx)clipse (>= 3.4.1 version)
```

# 📲 Contact

Fabio Luis Guia da Conceição

<a href="https://www.linkedin.com/in/fabio-luis-guia-da-conceição-77784741"><img src="https://img.shields.io/badge/linkedin%20-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>

---

<h5 align="center">
  &copy;2021/09 - <a href="https://github.com/Flgc">Fábio Luís</a>
</h5>
