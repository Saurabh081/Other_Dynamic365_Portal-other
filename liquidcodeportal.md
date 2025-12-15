// without using fetch querry fetch data from the fields of crm entiy 
here entiy is product 


{% assign product = entities['product'][request.params.id] %} // important code

<div data-component-theme="portalThemeColor8" class="row sectionBlockLayout text-left" style="display: flex; flex-wrap: wrap; margin: 0px; min-height: auto; padding: 8px 8px 0px;">
  <div class="container" style="display: flex; flex-wrap: wrap;">
    <div class="col-md-12 columnBlockLayout" style="flex-grow: 1; display: flex; flex-direction: column; min-width: 250px; padding: 16px; margin: 10px 0px;">
      <h2 style="text-align: left;">{% if product %}{{ product.name }}{% else %}ABE CraftCan 35 Canning Machine{% endif %}</h2>
      <p class="smallText" style="text-align: left; margin: 0px 0px 0px 0px;">Home / Assets / Food &amp; Beverage Processing / Bottling / {% if product %}{{ product.mm_productid }}{% else %}AM-100001{% endif %}</p>
    </div>
  </div>
</div>

<div data-component-theme="portalThemeColor8" class="row sectionBlockLayout text-left" style="display: flex; flex-wrap: wrap; padding: 8px; margin: 0px; min-height: auto; border-radius: 0px; background-image: linear-gradient(0deg, rgba(143, 149, 233, 0), rgba(143, 149, 233, 0));">
  <div class="container" style="padding: 0px; display: flex; flex-wrap: wrap; column-gap: 0px;">
    
    <div class="col-md-8 columnBlockLayout" style="flex-grow: 1; display: flex; flex-direction: column; min-width: 250px; margin: 10px 0px; padding: 16px; width: calc(66.6667% + 0px);">
      {% include 'Product Image Carousel' %}
      <!--<img src="/RBG001-CanCraft35-3.png" alt="RBG001-CanCraft35-3" name="RBG001-CanCraft35-3.png" style="width: 96%; height: 442px; max-width: 100%; border-radius: 3px 3px 3px 3px;" />
      <div class="row sectionBlockLayout" style="display: flex; flex-wrap: wrap; padding: 8px; margin: 0px; min-height: 15px;"></div>
      <div class="ppFlexContainer" style="display: flex;">
        <img src="/RBG001-CanCraft35-4.png" alt="RBG001-CanCraft35-4" name="RBG001-CanCraft35-4.png" style="width: 23%; height: 108px; max-width: 100%; border-radius: 3px 3px 3px 3px;" />
        <img src="/RBG001-CanCraft35-4.png" alt="RBG001-CanCraft35-4" name="RBG001-CanCraft35-4.png" style="width: 23%; height: 108px; max-width: 100%; border-radius: 3px 3px 3px 3px;" />
        <img src="/RBG001-CanCraft35-4.png" alt="RBG001-CanCraft35-4" name="RBG001-CanCraft35-4.png" style="width: 23%; height: 108px; max-width: 100%; border-radius: 3px 3px 3px 3px;" />
        <img src="/RBG001-CanCraft35-4.png" alt="RBG001-CanCraft35-4" name="RBG001-CanCraft35-4.png" style="width: 23%; height: 108px; max-width: 100%; border-radius: 3px 3px 3px 3px;" />
          -->
    </div>


    <div class="col-md-4 columnBlockLayout" style="flex-grow: 1; display: flex; flex-direction: column; min-width: 250px; margin: 10px 0px; padding: 16px; width: calc(33.3333% + 0px);">
      <h3 style="text-align: left; margin: 0px 0px 0px 0px; padding: 10px 10px 10px 10px; border-radius: 3px 3px 0px 0px; background-color: rgba(77, 50, 115, 1); font-size: 14px;">ID: {% if product %}{{ product.mm_productid }}{% else %}AM-100001{% endif %}</h3>
      <p style="background-color: rgba(249, 246, 254, 1); margin: 0px 0px 0px 0px; color: var(--portalThemeColor8); padding: 6px 6px 6px 10px; font-size: 24px;">
        <b aria-label="Price" style="position: relative;"> {% if product %}${{ product.price | round: 2 }} {% else %}$120,000 {% endif %} </b>
      </p>
      <p style="background-color: rgba(249, 246, 254, 1); margin: 0px 0px 0px 0px; color: var(--portalThemeColor8); padding: 6px 6px 6px 10px;">{% if product %}{{ product.mm_conditioncode }}{% else %}Used / Excellent{% endif %}</p>
      <p style="text-align: left; background-color: rgba(249, 246, 254, 1); margin: 0 0 0px 0; border-radius: 0px 0px 0px 0px; color: var(--portalThemeColor8); padding: 6px 6px 6px 10px;">Condition: {% if product %} {% if product.mm_conditioncode.Label %} {{ product.mm_conditioncode.Label }} {% else %} {{ product.mm_conditioncode }} {% endif %} {% else %} Used / Excellent {% endif %}</p>
      <p style="background-color: rgba(249, 246, 254, 1); margin: 0px 0px 0px 0px; color: var(--portalThemeColor8); padding: 6px 6px 6px 10px;">
        <b
          ><i><span>Nelson, NZ</span></i></b
        >
      </p>
      {% if product and product.mm_headline %}
      <p style="background-color: rgba(249, 246, 254, 1); margin: 0px 0px 0px 0px; color: var(--portalThemeColor8); padding: 6px 6px 6px 10px;">{{ product.mm_headline }}</p>
      {% endif %}

      <a href="/Assets-for-Sale/asset-enquiry" class="btn button1" style="width: auto;">Enquire Now</a>
    </div>
  </div>
</div>

<div data-component-theme="portalThemeColor8" class="row sectionBlockLayout text-left" style="display: flex; flex-wrap: wrap; margin: 0; min-height: auto; padding: 8px 8px 20px;">
  <div class="container" style="padding: 0px; display: flex; flex-wrap: wrap;">
    <div class="col-md-12 columnBlockLayout" style="flex-grow: 1; min-width: 250px; margin: 10px 0; padding: 16px;">
      <h3 style="text-align: left; margin: 10px 0 0; padding: 6px 10px; background-color: rgba(77, 50, 115, 1); border-radius: 3px 3px 0 0;">Details</h3>

      {% if product and product.mm_details %}
      <div style="text-align: left; background-color: rgba(249, 246, 254, 1); padding: 10px; border-radius: 0 0 3px 3px; color: var(--portalThemeColor8); font-size: 16px; line-height: 1.7;">
        {% assign details_lines = product.mm_details | newline_to_br | split: '<br />' %}
        <ul style="padding-left: 20px; list-style-type: none; margin-left: 0;">
          {% for line in details_lines %} {% assign trimmed = line | strip %} {% if trimmed != "" %}
          <li>{{ trimmed }}</li>
          {% endif %} {% endfor %}
        </ul>
      </div>
      {% endif %}
    </div>
  </div>
</div>
