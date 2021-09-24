REPORT ZKD_ABAP_OBJECT_INHERITANCE.
*Class method kullan#ld# s#n#f içerisinde s#n#f yarat#ld#.
*Car s#n#f#n#n elemanlar# tan#mland#
* static constructor yarat#ld#
* KAD#R DE#ER
* kadirdegr1997@gmail.com

*----------------------------------------------------------------------*
*       CLASS ford DEFINITION
*----------------------------------------------------------------------*
*
*----------------------------------------------------------------------*
CLASS ford DEFINITION.
  PUBLIC SECTION.

***** Define the CLASS CONSTRUCTOR
  CLASS-METHODS class_constructor.        "Static Constructor

    METHODS constructor
      IMPORTING
        p_model TYPE string.

  PROTECTED SECTION.
    DATA: model TYPE string.
    class-DATA: carlog type c LENGTH 40.

ENDCLASS.                    "ford DEFINITION

*----------------------------------------------------------------------*
*       CLASS mercedes DEFINITION
*----------------------------------------------------------------------*
*
*----------------------------------------------------------------------*
CLASS mercedes DEFINITION INHERITING FROM ford.
***** Redefine the CLASS CONSTRUCTOR
  PUBLIC SECTION.
    CLASS-METHODS class_constructor.        "Static Constructor
ENDCLASS.                    "mercedes DEFINITION

*----------------------------------------------------------------------*
*       CLASS audi DEFINITION
*----------------------------------------------------------------------*
*
*----------------------------------------------------------------------*
CLASS audi DEFINITION INHERITING FROM mercedes.
  PUBLIC SECTION.
***** Redefine the CLASS CONSTRUCTOR
  CLASS-METHODS class_constructor.        "Static Constructor

    METHODS constructor
      IMPORTING
        p_model TYPE string
        p_wheels TYPE i.

  PROTECTED SECTION.
    DATA: wheels TYPE i.

ENDCLASS.                    "audi DEFINITION

* IMPLEMENTATION

CLASS ford IMPLEMENTATION.
  METHOD class_constructor.
    carlog = 'FORD class constructor kullan#ld#'.
    WRITE: / carlog.
  ENDMETHOD.

  METHOD constructor.
    model = p_model.
  ENDMETHOD.                    "constructor
ENDCLASS.                    "ford IMPLEMENTATION

CLASS mercedes IMPLEMENTATION.
  METHOD class_constructor.
    carlog = 'MERCEDES class constructor kullan#ld#'.
    WRITE: / carlog.
  ENDMETHOD.          "constructor
ENDCLASS.                    "ford IMPLEMENTATION

*----------------------------------------------------------------------*
*       CLASS audi IMPLEMENTATION
*----------------------------------------------------------------------*
*
*----------------------------------------------------------------------*
CLASS audi IMPLEMENTATION.
  METHOD class_constructor.
    carlog = 'AUDI class constructor vkullan#ld#'.
    WRITE: / carlog.
  ENDMETHOD.          "constructor

  METHOD constructor.
    CALL METHOD super->constructor
      EXPORTING
        p_model = p_model.
    wheels = p_wheels.
  ENDMETHOD.                    "constructor
ENDCLASS.                    "audi IMPLEMENTATION

* Our program starts here.

DATA: my_ford       TYPE REF TO ford,
      my_mercedes   TYPE REF TO mercedes,
      my_audi       TYPE REF TO audi.

START-OF-SELECTION.

  CREATE OBJECT: my_audi      EXPORTING p_model = 'A4'
                                        p_wheels = 4,
                 my_ford      EXPORTING p_model = 'FOCUS',
                 my_mercedes  EXPORTING p_model = 'C-CLASS'.

  uline.
