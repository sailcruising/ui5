DATA:
ls_entity LIKE er_entity.

io_tech_request_context->get_converted_keys(
IMPORTING
es_key_values
= ls_entity ).

SELECT
SINGLE * INTO er_entity  FROM
zvt_categories where id_category = ls_entity-id_category.

select *
from zvt_categories into CORRESPONDING FIELDS OF table et_entityset.
