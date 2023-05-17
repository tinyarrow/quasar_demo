<template>
  <div>
    <q-splitter v-model="splitterModel">
      <template v-slot:before>
        <div class="q-pa-md">
          <q-tree
            :nodes="simple"
            node-key="label"
            selected-color="primary"
            v-model:selected="selected"
            default-expand-all
          />
        </div>
      </template>

      <template v-slot:separator>
        <q-avatar
          color="primary"
          text-color="white"
          size="40px"
          icon="drag_indicator"
        />
      </template>

      <template v-slot:after>
        <div class="sc-design q-mb-md">
          <div class="row q-px-sm">
            <div class="col-md-3" style="margin-right: 10px; margin-top: 10px">
              <sc-shadow>
                <q-card flat class="text-grey-9">
                  <q-card-section class="bg-white">
                    <q-avatar
                      color="green-1"
                      size="sm"
                      text-color="green"
                      class="q-mr-sm"
                      icon="visibility"
                    ></q-avatar>
                    <span>1234</span>
                    <span>
                      <q-chip
                        size="sm"
                        square
                        outline
                        color="green"
                        class="bg-green-1 float-right"
                        label="day"
                      ></q-chip>
                    </span>
                  </q-card-section>
                  <q-separator />
                  <q-card flat square class="q-pa-md">
                    <div style="height: 70px">
                      <q-item-label
                        class="text-grey-9 q-mb-md"
                        style="font-size: xx-large"
                      >
                        114514
                      </q-item-label>
                      <q-item-label class="q-mb-md">
                        <span class="q-mr-md">
                          2022
                          <q-icon size="xs" name="arrow_drop_up" color="red" />
                        </span>
                        <span>
                          05-15
                          <q-icon
                            size="xs"
                            name="arrow_drop_down"
                            color="info"
                          />
                        </span>
                      </q-item-label>
                    </div>
                    <q-separator spaced="15px" />
                    <q-item-label>
                      <span>total visitor</span>
                      <span class="float-right">280 万</span>
                    </q-item-label>
                  </q-card>
                </q-card>
              </sc-shadow>
            </div>
            <div class="col-md-5" style="margin-right: 10px; margin-top: 10px">
              <sc-shadow>
                <q-card flat class="q-pb-md">
                  <q-card-section>
                    <q-avatar
                      color="blue-1"
                      size="sm"
                      text-color="primary"
                      class="q-mr-sm"
                      icon="point_of_sale"
                    ></q-avatar>
                    <span>sales</span>
                    <span>
                      <q-icon
                        name="more_vert"
                        color="grey-7"
                        class="float-right"
                      ></q-icon>
                    </span>
                  </q-card-section>
                  <q-separator />
                  <q-item-label class="q-mt-md">
                    <ePie
                      ref="salePie"
                      :option="salePieData.option"
                      :height="salePieData.height"
                    />
                  </q-item-label>
                </q-card>
              </sc-shadow>
            </div>
          </div>
        </div>

        <q-tab-panels
          v-model="selected"
          animated
          transition-prev="jump-up"
          transition-next="jump-up"
        >
          <q-tab-panel name="Relax Hotel">
            <div class="text-h4 q-mb-md">Welcome</div>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
          </q-tab-panel>

          <q-tab-panel name="Food">
            <div class="text-h4 q-mb-md">Food</div>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
          </q-tab-panel>

          <q-tab-panel name="Room service">
            <div class="text-h4 q-mb-md">Room service</div>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
          </q-tab-panel>

          <q-tab-panel name="Room view">
            <div class="text-h4 q-mb-md">Room view</div>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
              praesentium cumque magnam odio iure quidem, quod illum numquam
              possimus obcaecati commodi minima assumenda consectetur culpa fuga
              nulla ullam. In, libero.
            </p>
          </q-tab-panel>
        </q-tab-panels>
      </template>
    </q-splitter>
  </div>
</template>

<script>
import { ref } from 'vue';
import ePie from 'src/components/Epie.vue';

const pieData = {
  height: 260,
  option: {
    legend: {
      data: [],
    },
    series: {
      name: 'test',
      data: [],
    },
  },
};
pieData.option.series.data = [
  { name: 'Pass', value: 100 },
  { name: 'Fail', value: 10 },
  { name: 'Warning', value: 5 },
];
pieData.option.legend.data = ['Pass', 'Fail', 'Warning'];

export default {
  components: {
    ePie,
  },
  setup() {
    return {
      splitterModel: ref(20),
      selected: ref('Food'),
      items: ['1', '2'],
      leftDrawerOpen: true,
      salePieData: pieData,

      simple: [
        {
          label: 'Relax Hotel',
          children: [
            {
              label: 'Food',
              icon: 'restaurant_menu',
            },
            {
              label: 'Room service',
              icon: 'room_service',
            },
            {
              label: 'Room view',
              icon: 'photo',
            },
          ],
        },
      ],
    };
  },
  methods: {
    onNodeSelected() {
      console.log('ff:', this.selected);
    },
  },
};
</script>
