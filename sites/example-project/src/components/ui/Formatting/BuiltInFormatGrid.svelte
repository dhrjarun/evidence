<script>
  import "./format-grid.css";
  import { defaultExample, formatExample } from "$lib/modules/formatting";
  export let formats;
</script>

<table>
  <thead>
    <th class="align_left narrow_column">Format Tag</th>
    <th class="align_left wide_column">Format Code</th>
    <th class="align_left wide_column">Example Input</th>
    <th class="align_right wide_column">Example Output</th>
  </thead>
  {#each formats as format}
    <tr>
      <td>{format.formatTag} </td>
      <td>{format.formatCode} </td>
      <td>
        <input
          id="id_format_row{format.formatTag}"
          placeholder={format.exampleInput || defaultExample(format.valueType)}
          bind:value={format.userInput}
          on:blur={(format.userInput = undefined)}
          class="align_left input_box"
        />
      </td>
      <td class="align_right">{formatExample(format)}</td>
    </tr>
  {/each}
</table>


