########################################
# ADDRESS
########################################
{{ address.city }}
{{ address.country_code }}
{{ address.country_name }}
{{ address.created_at }}
{{ address.location }}
{{ address.postal_address }}
{{ address.state }}
{{ address.street }}
{{ address.street_line_1 }}
{{ address.street_line_2 }}
{{ address.updated_at }}
{{ address.zip }}

########################################
# APP
########################################
{{ app.name }}

########################################
# BACKGROUND CHECK
########################################
{{ person.background_check.cleared_on }}
{{ person.background_check.expires_on }}
{{ person.background_check.note }}
{{ person.background_check.status }}

########################################
# DATE (birthdate object confirmed)
########################################
{{ person.birthdate.day }}
{{ person.birthdate.month }}
{{ person.birthdate.year }}

########################################
# EMAIL
########################################
{{ email.address }}
{{ email.created_at }}
{{ email.location }}
{{ email.updated_at }}

########################################
# FIELD
########################################
{{ field.data_type }}
{{ field.date_value }}
{{ field.id }}
{{ field.name }}
{{ field.section_header }}   {# likely another FIELD object #}
{{ field.sequence }}
{{ field.slug }}
{{ field.tab }}              {# TAB object #}
{{ field.url }}
{{ field.value }}
{{ field.value_created_at }}
{{ field.value_updated_at }}

{% for value in field.values %}
  {{ value }}
{% endfor %}

########################################
# HOUSEHOLD
########################################

# Arrays of PERSON objects (confirmed by schema)
{% for person in household.active_adults %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.active_children %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.active_other_adults %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.active_parents_guardians %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.adults %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.children %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{{ household.created_at }}
{{ household.id }}
{{ household.member_count }}
{{ household.name }}

{% for person in household.other_adults %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.parents_guardians %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{% for person in household.people %}
  {{ person.first_name }} {{ person.last_name }} {{ person.id }}
{% endfor %}

{{ household.photo_url }}

# Nested objects
{{ household.primary_address.city }}
{{ household.primary_address.state }}
{{ household.primary_address.zip }}

{{ household.primary_contact.first_name }}
{{ household.primary_contact.last_name }}

{{ household.primary_phone_number.number }}

{{ household.updated_at }}

########################################
# LIST
########################################

# LIST COLUMN (explicit)
{{ list_column.id }}
{{ list_column.identifier }}
{{ list_column.name }}

# Columns array
{% for column in list.columns %}
  {{ column.id }}
  {{ column.identifier }}
  {{ column.name }}
{% endfor %}

{{ list.created_at }}
{{ list.created_by.first_name }} {{ list.created_by.last_name }}
{{ list.id }}
{{ list.name }}
{{ list.updated_at }}
{{ list.updated_by.first_name }} {{ list.updated_by.last_name }}

########################################
# LIST RESULT
########################################
{{ list_result_drop.id }}
{{ list_result_drop.person.first_name }}
{{ list_result_drop.person.last_name }}
{{ list_result_drop.person.id }}

########################################
# NOTE
########################################
{{ note.author.first_name }} {{ note.author.last_name }}
{{ note.category }}
{{ note.date }}
{{ note.message }}

########################################
# ORGANIZATION
########################################
{{ organization.created_at }}
{{ organization.id }}
{{ organization.logo_url }}
{{ organization.name }}
{{ organization.subdomain }}

{% for tab in organization.tabs %}
  {{ tab.id }}
  {{ tab.name }}
  {{ tab.sequence }}
  {{ tab.slug }}
{% endfor %}

{{ organization.time_zone }}
{{ organization.updated_at }}

########################################
# PERSON
########################################
{{ person.active }}

{% for address in person.addresses %}
  {{ address.city }} {{ address.state }} {{ address.zip }}
{% endfor %}

{{ person.age }}
{{ person.anniversary }}
{{ person.anniversary_day }}

{% for app in person.apps %}
  {{ app.name }}
{% endfor %}

{{ person.birthdate.day }}
{{ person.birthdate.month }}
{{ person.birthdate.year }}

{{ person.birthday }}
{{ person.child }}
{{ person.created_at }}

# custom_tabs is OBJECT → structure unknown
{{ person.custom_tabs }}

{% for email in person.emails %}
  {{ email.address }}
{% endfor %}

{% for field in person.fields %}
  {{ field.name }}: {{ field.value }}
{% endfor %}

{{ person.first_initial }}
{{ person.first_name }}
{{ person.gender }}
{{ person.given_name }}
{{ person.grade }}
{{ person.grade_name }}
{{ person.graduation_year }}

{% for household in person.households %}
  {{ household.name }}
{% endfor %}

{{ person.id }}
{{ person.inactive }}
{{ person.inactive_reason }}
{{ person.last_initial }}
{{ person.last_name }}
{{ person.marital_status }}
{{ person.medical_notes }}

{% for note in person.notes %}
  {{ note.message }}
{% endfor %}

{{ person.pending }}

{% for phone_number in person.phone_numbers %}
  {{ phone_number.number }}
{% endfor %}

{{ person.photo_url }}

{{ person.primary_address.city }}
{{ person.primary_address.state }}
{{ person.primary_address.zip }}

{{ person.primary_campus_name }}

{% for contact in person.primary_contacts %}
  {{ contact.first_name }} {{ contact.last_name }}
{% endfor %}

{{ person.primary_email.address }}
{{ person.primary_phone_number.number }}
{{ person.primary_zip_code }}

{{ person.school }}
{{ person.school_type }}
{{ person.status }}

{% for tab in person.tabs %}
  {{ tab.name }}
{% endfor %}

{{ person.updated_at }}

########################################
# PHONE NUMBER
########################################
{{ phone_number.created_at }}
{{ phone_number.location }}
{{ phone_number.number }}
{{ phone_number.updated_at }}

########################################
# REPORT
########################################
{{ report.created_at }}
{{ report.created_by.first_name }} {{ report.created_by.last_name }}
{{ report.id }}
{{ report.name }}
{{ report.updated_at }}
{{ report.updated_by.first_name }} {{ report.updated_by.last_name }}

########################################
# TAB
########################################
{% for field in tab.fields %}
  {{ field.name }}: {{ field.value }}
{% endfor %}

{{ tab.id }}
{{ tab.name }}
{{ tab.sequence }}
{{ tab.slug }}
