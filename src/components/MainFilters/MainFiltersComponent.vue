<script>
import ButtonSelect from "./Elements/ButtonSelectElement.vue";
import Input from "./Elements/BasicInputElement.vue";
import Table from "./Elements/TableElement.vue";
import SortSelect from "./Elements/SortSelectElement.vue";
import Tag from "./Elements/TagElement.vue";
import Block from "@/components/MainFilters/Elements/Block/Block.vue";
import BlockRow from "@/components/MainFilters/Elements/Block/BlockRow.vue";

export default {
  name: "MainFilters",
  components: {BlockRow, Block, Tag, SortSelect, Table, Input, ButtonSelect },
  methods: {
    getRandomNumbers(number) {
      let someData = []
      for (let i = 0; i < number; i++) {
        someData.push(Math.floor(Math.random() * number));
      }
      return someData
    }
  },
}
</script>

<template>
  <div class="flex flex-col gap-4">
    <Block>
      <Input>
        <template #title>Country*</template>
        <template #required>
          <option value="0" selected disabled hidden>Not selected</option>
          <option v-for="option in getRandomNumbers(10)" :key="option">{{ option }}</option>
        </template>
      </Input>

      <BlockRow>
        <Input>
          <template #title>Type IP rights*</template>
          <template #required>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(8)" :key="option">{{ option }}</option>
          </template>
        </Input>

        <Input>
          <template #title>Current status</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(5)" :key="option">{{ option }}</option>
          </template>
        </Input>
      </BlockRow>

      <Input>
        <template #title>Search word element</template>
        <template #input />
      </Input>
    </Block>

    <Block>
      <template #name>Name, number</template>

      <BlockRow>
        <Input>
          <template #title>Search by number type</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(4)" :key="option">{{ option }}</option>
          </template>
        </Input>

        <Input>
          <template #title>Number</template>
          <template #input />
        </Input>
      </BlockRow>

      <BlockRow>
        <Input>
          <template #title>Search by name type</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(12)" :key="option">{{ option }}</option>
          </template>
        </Input>

        <Input>
          <template #title>Name</template>
          <template #input />
        </Input>
      </BlockRow>
    </Block>

    <Block>
      <template #name>Invoice</template>

      <BlockRow>
        <Input>
          <template #title>Payment method</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(5)" :key="option">{{ option }}</option>
          </template>
        </Input>

        <Input>
          <template #title>Payment status</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(3)" :key="option">{{ option }}</option>
          </template>
        </Input>
      </BlockRow>
    </Block>

    <Block>
      <template #name>Orders, renewals</template>

      <BlockRow>
        <Input>
          <template #title>Order status</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(5)" :key="option">{{ option }}</option>
          </template>
        </Input>

        <Input>
          <template #title>Renewal status</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(9)" :key="option">{{ option }}</option>
          </template>
        </Input>
      </BlockRow>

      <BlockRow class="max-md:flex-col gap-y-0">
        <Input>
          <template #title>Filter by date</template>
          <template #options>
            <option value="0" selected disabled hidden>Not selected</option>
            <option v-for="option in getRandomNumbers(3)" :key="option">{{ option }}</option>
          </template>
        </Input>

        <BlockRow>
          <Input>
            <template #title>Date, From</template>
            <template #date />
          </Input>
          <Input>
            <template #title>Date, To</template>
            <template #date />
          </Input>
        </BlockRow>
      </BlockRow>
    </Block>

    <Block class="flex gap-2 max-md:flex-col">
      <Tag>Trademarks</Tag>
      <Tag>Active</Tag>
      <Tag>Australia</Tag>
      <Tag>Registered</Tag>
      <Tag>Expiry date: 01.01.2020-05.10.2022</Tag>
    </Block>

    <Block>
      <template #name>Data columns</template>

      <BlockRow class="max-md:flex-col mt-4 max-md:gap-y-0 gap-x-0">
        <Table>Имя столбца таблицы 1</Table>
        <Table><template #full>Имя столбца таблицы 2</template></Table>
        <Table>Имя столбца таблицы 3</Table>
        <Table><template #full>Имя столбца таблицы 2</template></Table>
        <Table>Имя столбца таблицы 5</Table>
        <Table><template #full>Имя столбца таблицы 2</template></Table>
      </BlockRow>

      <BlockRow class="max-md:flex-col mt-2 max-md:gap-y-0 gap-x-0">
        <Table><template #full>Имя столбца таблицы 2</template></Table>
        <Table>Имя столбца таблицы 1</Table>
        <Table><template #full>Имя столбца таблицы 2</template></Table>
        <Table>Имя столбца таблицы 3</Table>
        <Table><template #full>Имя столбца таблицы 2</template></Table>
        <Table>Имя столбца таблицы 5</Table>
      </BlockRow>
    </Block>

    <Block class="flex gap-x-[10%] items-start justify-start max-md:flex-col">
      <template #name>Сортировка</template>

      <BlockRow class="max-md:flex-col max-md:mt-2 justify-between flex-wrap gap-0">
        <SortSelect>
          <option value="0">Сперва новые</option>
          <option>Сперва старые</option>
        </SortSelect>

        <SortSelect>
          <option value="0">Только необработанные</option>
          <option>Сперва старые</option>
        </SortSelect>

        <SortSelect>
          <option value="0">Есть в клиентах</option>
          <option>Сперва старые</option>
        </SortSelect>

        <SortSelect>
          <option value="0">Есть в поставщиках</option>
          <option>Сперва старые</option>
        </SortSelect>

        <SortSelect>
          <option value="0">Есть в группе поставщиков</option>
          <option>Сперва старые</option>
        </SortSelect>
      </BlockRow>
    </Block>

    <Block class="flex gap-x-[10%] max-md:flex-col max-md:gap-2">
      <template #name>Вид</template>
      <BlockRow class="gap-[5%]">
        <ButtonSelect>Скрывать изображения</ButtonSelect>
        <ButtonSelect>Показывать изображения</ButtonSelect>
      </BlockRow>
    </Block>
  </div>
</template>