<script>
  import Example from '../Example.svelte';
  import Sample from './Sample.svelte';
  import sampleSource from '!!raw-loader!./Sample.svelte';
  import MaterialSource from '!!raw-loader!./Material.svelte';
  import SizeDefaultSource from '!!raw-loader!./SizeDefault.svelte';
  import SizeMaterialSource from '!!raw-loader!./SizeMaterial.svelte';
  import ButtonAddonsSource from '!!raw-loader!./ButtonAddons.svelte';
  import MultipleInputGroupSource from '!!raw-loader!./MultipleInputGroup.svelte';
  import MultipleAddonsSource from '!!raw-loader!./MultipleAddons.svelte';
  import Title from "../Title.svelte";
  import MDBRow from "../../src/MDBRow.svelte";
  import MDBCol from "../../src/MDBCol.svelte";
  import Material from "./Material.svelte";
  import SizeDefault from "./SizeDefault.svelte";
  import SizeMaterial from "./SizeMaterial.svelte";
  import MultipleInputGroup from "./MultipleInputGroup.svelte";
  import MultipleAddons from "./MultipleAddons.svelte";
  import ButtonAddons from "./ButtonAddons.svelte";

</script>

<Title title="Input Group">
</Title>

<MDBRow>
  <MDBCol md="6">
    <Example title="Basic Bootstrap" source={sampleSource}>
      <Sample/>
    </Example>
  </MDBCol>
  <MDBCol md="6">
    <Example title="Material Bootstrap" source={MaterialSource}>
      <Material/>
    </Example>
  </MDBCol>
</MDBRow>
<MDBRow>
  <MDBCol md="6">
    <Example title="Sizing Basic in Bootstrap" source={SizeDefaultSource}>
      <SizeDefault/>
    </Example>
  </MDBCol>
  <MDBCol md="6">
    <Example title="Sizing in Material" source={SizeMaterialSource}>
      <SizeMaterial/>
    </Example>
  </MDBCol>
</MDBRow>
<Example title="Multiple Input Group"
         description='<p>If you wanna use multiple inputs you can pass the inputs as a slot <code>slot="input"</code> </p>'
         source={MultipleInputGroupSource}>
  <MultipleInputGroup/>
</Example>
<Example title="Multiple Addons" source={MultipleAddonsSource}>
  <MultipleAddons/>
</Example>
<Example source={ButtonAddonsSource} title="Button Addons">
  <ButtonAddons/>
</Example>
